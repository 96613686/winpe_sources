# SetIOProc

- ea: `0x180011a18`
- end: `0x180011b5d`
- name: `SetIOProc`
- size: `325`
- prototype: ``
- caller_count: `4`
- callee_count: `5`
- tags: ``

## callers

- `0x180011f20`
- `0x180012180`
- `0x180012370`
- `0x1800124d0`

## callees

- `0x1800106c0`
- `0x180010700`
- `0x1800119dc`
- `0x180011a18`
- `0x1800128e0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x180011a61`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x180011a61`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180011b10`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180011b10`

## pseudocode

```c
void __fastcall SetIOProc(const wchar_t *a1, __int64 a2)
{
  wchar_t *v4; // rax
  wchar_t *v5; // rcx
  unsigned __int64 v6; // rax
  __int64 v7; // rdx
  int v8; // eax
  WCHAR *v9; // rcx
  WCHAR v10; // r9
  WCHAR v11; // dx
  __int64 CurrentThreadId; // rdx
  __int64 IOProc; // rax
  __int64 (__fastcall *v14)(char *, int, void *, const WCHAR *); // rax
  WCHAR sz[8]; // [rsp+20h] [rbp-28h] BYREF

  if ( !*(_QWORD *)(a2 + 8) )
  {
    if ( !*(_DWORD *)(a2 + 4) )
    {
      if ( a1 )
      {
        v4 = wcsrchr(a1, 0x2Bu);
        v5 = v4;
        if ( v4 )
        {
          if ( v4 > a1 )
          {
            do
            {
              v6 = *v5;
              LOWORD(v6) = v6 - 46;
              if ( (unsigned __int16)v6 <= 0x2Eu )
              {
                v7 = 0x400000001001LL;
                if ( _bittest64(&v7, v6) )
                  break;
              }
              --v5;
            }
            while ( v5 > a1 );
          }
          if ( *v5 == 46 )
          {
            v8 = 0;
            v9 = v5 + 1;
            while ( (unsigned __int64)v8 < 4 )
            {
              v10 = *v9;
              if ( *v9 == 43 )
              {
                if ( (unsigned __int64)(2LL * v8) >= 0xA )
                  _report_rangecheckfailure();
                v11 = 0;
              }
              else
              {
                ++v9;
                v11 = v10;
              }
              sz[v8++] = v11;
            }
            sz[4] = 0;
            *(_DWORD *)(a2 + 4) = mmioStringToFOURCCW(sz, 0x10u);
          }
        }
      }
      if ( !*(_DWORD *)(a2 + 4) )
        *(_DWORD *)(a2 + 4) = 542330692;
    }
    CurrentThreadId = *(_QWORD *)(a2 + 20);
    if ( !CurrentThreadId )
      CurrentThreadId = GetCurrentThreadId();
    IOProc = FindIOProc(*(unsigned int *)(a2 + 4), CurrentThreadId);
    if ( !IOProc || (v14 = *(__int64 (__fastcall **)(char *, int, void *, const WCHAR *))(IOProc + 8)) == 0 )
    {
      v14 = mmioDOSIOProc;
      *(_DWORD *)(a2 + 84) = 0;
    }
    *(_QWORD *)(a2 + 8) = v14;
  }
}

```

## disassembly

```asm
0x180011a18  mov     [rsp+arg_10], rbx
0x180011a1d  mov     [rsp+arg_18], rbp
0x180011a22  push    rdi
0x180011a23  sub     rsp, 40h
0x180011a27  mov     rax, cs:__security_cookie
0x180011a2e  xor     rax, rsp
0x180011a31  mov     [rsp+48h+var_18], rax
0x180011a36  cmp     qword ptr [rdx+8], 0
0x180011a3b  mov     rbx, rdx
0x180011a3e  mov     rdi, rcx
0x180011a41  jnz     loc_180011B40
0x180011a47  cmp     dword ptr [rdx+4], 0
0x180011a4b  jnz     loc_180011B07
0x180011a51  test    rcx, rcx
0x180011a54  jz      loc_180011AFA
0x180011a5a  mov     ebp, 2Bh ; '+'
0x180011a5f  mov     edx, ebp; Ch
0x180011a61  call    cs:__imp_wcsrchr
0x180011a67  mov     rcx, rax
0x180011a6a  test    rax, rax
0x180011a6d  jz      loc_180011AFA
0x180011a73  cmp     rax, rdi
0x180011a76  jbe     short loc_180011A9E
0x180011a78  movzx   eax, word ptr [rcx]
0x180011a7b  sub     ax, 2Eh ; '.'
0x180011a7f  cmp     ax, 2Eh ; '.'
0x180011a83  ja      short loc_180011A95
0x180011a85  mov     rdx, 400000001001h
0x180011a8f  bt      rdx, rax
0x180011a93  jb      short loc_180011A9E
0x180011a95  sub     rcx, 2
0x180011a99  cmp     rcx, rdi
0x180011a9c  ja      short loc_180011A78
0x180011a9e  cmp     word ptr [rcx], 2Eh ; '.'
0x180011aa2  jnz     short loc_180011AFA
0x180011aa4  xor     eax, eax
0x180011aa6  add     rcx, 2
0x180011aaa  movsxd  rdx, eax
0x180011aad  cmp     rdx, 4
0x180011ab1  jnb     short loc_180011AE3
0x180011ab3  movzx   r9d, word ptr [rcx]
0x180011ab7  lea     r8, [rdx+rdx]
0x180011abb  cmp     r9w, bp
0x180011abf  jnz     short loc_180011ACB
0x180011ac1  cmp     r8, 0Ah
0x180011ac5  jnb     short loc_180011ADD
0x180011ac7  xor     edx, edx
0x180011ac9  jmp     short loc_180011AD3
0x180011acb  add     rcx, 2
0x180011acf  movzx   edx, r9w
0x180011ad3  mov     [rsp+r8+48h+sz], dx
0x180011ad9  inc     eax
0x180011adb  jmp     short loc_180011AAA
0x180011add  call    __report_rangecheckfailure
0x180011ae3  xor     eax, eax
0x180011ae5  lea     rcx, [rsp+48h+sz]; sz
0x180011aea  mov     [rsp+48h+var_20], ax
0x180011aef  lea     edx, [rax+10h]; uFlags
0x180011af2  call    mmioStringToFOURCCW
0x180011af7  mov     [rbx+4], eax
0x180011afa  cmp     dword ptr [rbx+4], 0
0x180011afe  jnz     short loc_180011B07
0x180011b00  mov     dword ptr [rbx+4], 20534F44h
0x180011b07  mov     rdx, [rbx+14h]
0x180011b0b  test    rdx, rdx
0x180011b0e  jnz     short loc_180011B18
0x180011b10  call    cs:__imp_GetCurrentThreadId
0x180011b16  mov     edx, eax
0x180011b18  mov     ecx, [rbx+4]
0x180011b1b  call    FindIOProc
0x180011b20  test    rax, rax
0x180011b23  jz      short loc_180011B2E
0x180011b25  mov     rax, [rax+8]
0x180011b29  test    rax, rax
0x180011b2c  jnz     short loc_180011B3C
0x180011b2e  lea     rax, ?mmioDOSIOProc@@YA_JPEADI_J1@Z; mmioDOSIOProc(char *,uint,__int64,__int64)
0x180011b35  mov     dword ptr [rbx+54h], 0
0x180011b3c  mov     [rbx+8], rax
0x180011b40  mov     rcx, [rsp+48h+var_18]
0x180011b45  xor     rcx, rsp; StackCookie
0x180011b48  call    __security_check_cookie
0x180011b4d  mov     rbx, [rsp+48h+arg_10]
0x180011b52  mov     rbp, [rsp+48h+arg_18]
0x180011b57  add     rsp, 40h
0x180011b5b  pop     rdi
0x180011b5c  retn
```
