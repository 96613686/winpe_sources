# FaxGetServicePrintersA

- ea: `0x18000fd80`
- end: `0x18000fecd`
- name: `FaxGetServicePrintersA`
- size: `333`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `service_task`

## callees

- `0x18000abe4`
- `0x18000ac14`
- `0x18000fd80`
- `0x18000fee0`
- `0x1800279f0`
- `0x18002bb58`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18000fdf8`
- `KERNEL32!GetLastError` at `0x18000fe95`
- `KERNEL32!GetLastError` at `0x18000fdf8`
- `KERNEL32!GetLastError` at `0x18000fe95`

## pseudocode

```c
__int64 __fastcall FaxGetServicePrintersA(__int64 a1, LPVOID *a2, _DWORD *a3)
{
  DWORD LastError; // eax
  __int64 v8; // rbx
  DWORD v9; // eax

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 321, &WPP_6aa9d578c4393c02b9eb8137eb0c030f_Traceguids);
  }
  if ( !(unsigned int)FaxGetServicePrintersW(a1, a2, a3) )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      LastError = GetLastError();
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 322, &WPP_6aa9d578c4393c02b9eb8137eb0c030f_Traceguids, LastError);
    }
    return 0;
  }
  v8 = 0;
  if ( *a3 )
  {
    while ( (unsigned int)ConvertUnicodeStringInPlace(*((LPCWCH *)*a2 + 3 * v8))
         && (unsigned int)ConvertUnicodeStringInPlace(*((LPCWCH *)*a2 + 3 * v8 + 2))
         && (unsigned int)ConvertUnicodeStringInPlace(*((LPCWCH *)*a2 + 3 * v8 + 1)) )
    {
      v8 = (unsigned int)(v8 + 1);
      if ( (unsigned int)v8 >= *a3 )
        return 1;
    }
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v9 = GetLastError();
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 323, &WPP_6aa9d578c4393c02b9eb8137eb0c030f_Traceguids, v9);
    }
    pMemFree(*a2);
    return 0;
  }
  return 1;
}

```

## disassembly

```asm
0x18000fd80  push    rbx
0x18000fd82  push    rbp
0x18000fd83  push    rsi
0x18000fd84  push    rdi
0x18000fd85  push    r15
0x18000fd87  sub     rsp, 20h
0x18000fd8b  mov     rsi, r8
0x18000fd8e  mov     rdi, rdx
0x18000fd91  mov     rbx, rcx
0x18000fd94  mov     rcx, cs:WPP_GLOBAL_Control
0x18000fd9b  lea     r15, WPP_GLOBAL_Control
0x18000fda2  cmp     rcx, r15
0x18000fda5  jz      short loc_18000FDCB
0x18000fda7  test    dword ptr [rcx+1Ch], 1000h
0x18000fdae  jz      short loc_18000FDCB
0x18000fdb0  cmp     byte ptr [rcx+19h], 5
0x18000fdb4  jb      short loc_18000FDCB
0x18000fdb6  mov     rcx, [rcx+10h]
0x18000fdba  lea     r8, WPP_6aa9d578c4393c02b9eb8137eb0c030f_Traceguids
0x18000fdc1  mov     edx, 141h
0x18000fdc6  call    WPP_SF_
0x18000fdcb  mov     r8, rsi
0x18000fdce  mov     rdx, rdi
0x18000fdd1  mov     rcx, rbx
0x18000fdd4  call    FaxGetServicePrintersW
0x18000fdd9  test    eax, eax
0x18000fddb  jnz     short loc_18000FE27
0x18000fddd  mov     rax, cs:WPP_GLOBAL_Control
0x18000fde4  cmp     rax, r15
0x18000fde7  jz      short loc_18000FE23
0x18000fde9  test    dword ptr [rax+1Ch], 1000h
0x18000fdf0  jz      short loc_18000FE23
0x18000fdf2  cmp     byte ptr [rax+19h], 2
0x18000fdf6  jb      short loc_18000FE23
0x18000fdf8  call    cs:__imp_GetLastError
0x18000fdff  nop     dword ptr [rax+rax+00h]
0x18000fe04  mov     rcx, cs:WPP_GLOBAL_Control
0x18000fe0b  lea     r8, WPP_6aa9d578c4393c02b9eb8137eb0c030f_Traceguids
0x18000fe12  mov     edx, 142h
0x18000fe17  mov     r9d, eax
0x18000fe1a  mov     rcx, [rcx+10h]
0x18000fe1e  call    WPP_SF_d
0x18000fe23  xor     eax, eax
0x18000fe25  jmp     short loc_18000FE6E
0x18000fe27  xor     ebx, ebx
0x18000fe29  cmp     [rsi], ebx
0x18000fe2b  jbe     short loc_18000FE69
0x18000fe2d  mov     rcx, [rdi]
0x18000fe30  lea     rbp, [rbx+rbx*2]
0x18000fe34  mov     rcx, [rcx+rbp*8]; lpWideCharStr
0x18000fe38  call    ?ConvertUnicodeStringInPlace@@YAHPEBG@Z; ConvertUnicodeStringInPlace(ushort const *)
0x18000fe3d  test    eax, eax
0x18000fe3f  jz      short loc_18000FE7A
0x18000fe41  mov     rcx, [rdi]
0x18000fe44  mov     rcx, [rcx+rbp*8+10h]; lpWideCharStr
0x18000fe49  call    ?ConvertUnicodeStringInPlace@@YAHPEBG@Z; ConvertUnicodeStringInPlace(ushort const *)
0x18000fe4e  test    eax, eax
0x18000fe50  jz      short loc_18000FE7A
0x18000fe52  mov     rcx, [rdi]
0x18000fe55  mov     rcx, [rcx+rbp*8+8]; lpWideCharStr
0x18000fe5a  call    ?ConvertUnicodeStringInPlace@@YAHPEBG@Z; ConvertUnicodeStringInPlace(ushort const *)
0x18000fe5f  test    eax, eax
0x18000fe61  jz      short loc_18000FE7A
0x18000fe63  inc     ebx
0x18000fe65  cmp     ebx, [rsi]
0x18000fe67  jb      short loc_18000FE2D
0x18000fe69  mov     eax, 1
0x18000fe6e  add     rsp, 20h
0x18000fe72  pop     r15
0x18000fe74  pop     rdi
0x18000fe75  pop     rsi
0x18000fe76  pop     rbp
0x18000fe77  pop     rbx
0x18000fe78  retn
0x18000fe7a  mov     rax, cs:WPP_GLOBAL_Control
0x18000fe81  cmp     rax, r15
0x18000fe84  jz      short loc_18000FEC0
0x18000fe86  test    dword ptr [rax+1Ch], 1000h
0x18000fe8d  jz      short loc_18000FEC0
0x18000fe8f  cmp     byte ptr [rax+19h], 2
0x18000fe93  jb      short loc_18000FEC0
0x18000fe95  call    cs:__imp_GetLastError
0x18000fe9c  nop     dword ptr [rax+rax+00h]
0x18000fea1  mov     rcx, cs:WPP_GLOBAL_Control
0x18000fea8  lea     r8, WPP_6aa9d578c4393c02b9eb8137eb0c030f_Traceguids
0x18000feaf  mov     edx, 143h
0x18000feb4  mov     r9d, eax
0x18000feb7  mov     rcx, [rcx+10h]
0x18000febb  call    WPP_SF_d
0x18000fec0  mov     rcx, [rdi]; lpMem
0x18000fec3  call    pMemFree
0x18000fec8  jmp     loc_18000FE23
```
