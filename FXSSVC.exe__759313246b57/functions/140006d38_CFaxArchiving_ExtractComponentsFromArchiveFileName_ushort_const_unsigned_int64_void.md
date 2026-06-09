# CFaxArchiving::ExtractComponentsFromArchiveFileName(ushort const *,unsigned __int64 *,void * *)

- ea: `0x140006d38`
- end: `0x140006fae`
- name: `?ExtractComponentsFromArchiveFileName@CFaxArchiving@@QEAAKPEBGPEA_KPEAPEAX@Z`
- size: `630`
- prototype: `__int64 __fastcall(CFaxArchiving *this, const unsigned __int16 *, unsigned __int64 *, void **)`
- caller_count: `6`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14000610c`
- `0x140009378`
- `0x14000a330`
- `0x1400135d0`
- `0x140015384`
- `0x14001d790`

## callees

- `0x140002c73`
- `0x140004c78`
- `0x140004ca8`
- `0x140006d38`
- `0x140086ec0`

## import_xrefs

- `ADVAPI32!ConvertStringSidToSidW` at `0x140006f09`
- `ADVAPI32!ConvertStringSidToSidW` at `0x140006f09`
- `KERNEL32!GetLastError` at `0x140006f19`
- `KERNEL32!GetLastError` at `0x140006f19`
- `KERNEL32!LocalFree` at `0x140006f69`
- `KERNEL32!LocalFree` at `0x140006f69`
- `msvcrt!_wcsnicmp` at `0x140006edc`
- `msvcrt!_wcsnicmp` at `0x140006edc`
- `msvcrt!swscanf` at `0x140006e97`
- `msvcrt!swscanf` at `0x140006e97`
- `msvcrt!wcschr` at `0x140006e06`
- `msvcrt!wcschr` at `0x140006e53`
- `msvcrt!wcschr` at `0x140006e06`
- `msvcrt!wcschr` at `0x140006e53`

## pseudocode

```c
__int64 __fastcall CFaxArchiving::ExtractComponentsFromArchiveFileName(
        CFaxArchiving *this,
        const unsigned __int16 *a2,
        unsigned __int64 *a3,
        void **a4)
{
  CMapDeviceId *v7; // rcx
  unsigned __int64 v8; // rax
  wchar_t *v10; // rax
  CMapDeviceId *v11; // rcx
  __int64 v12; // rdx
  DWORD v13; // ebx
  DWORD LastError; // eax
  PSID Sid; // [rsp+20h] [rbp-258h] BYREF
  unsigned __int64 v16; // [rsp+28h] [rbp-250h] BYREF
  wchar_t String1[264]; // [rsp+30h] [rbp-248h] BYREF

  memset_0(String1, 0, 0x208u);
  v16 = 0;
  v7 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 187, &WPP_b5057cf466d13e046d0380d31f78638c_Traceguids);
    v7 = WPP_GLOBAL_Control;
  }
  v8 = -1;
  do
    ++v8;
  while ( a2[v8] );
  if ( v8 < 0x104 )
  {
    v10 = wcschr(a2, 0x24u);
    if ( v10 )
    {
      if ( wcschr(v10 + 1, 0x24u) )
      {
        v11 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          return 1009;
        }
        v12 = 190;
      }
      else
      {
        if ( swscanf(a2, L"%[^$]$%I64x", String1, &v16) == 2 )
        {
          if ( _wcsnicmp(String1, L"UnAssigned", 0xBu) )
          {
            Sid = 0;
            if ( !ConvertStringSidToSidW(String1, &Sid) )
            {
              LastError = GetLastError();
              v13 = LastError;
              if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
              {
                WPP_SF_d(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  192,
                  &WPP_b5057cf466d13e046d0380d31f78638c_Traceguids,
                  LastError);
              }
              return v13;
            }
            if ( a4 )
              *a4 = Sid;
            else
              LocalFree(Sid);
          }
          else if ( a4 )
          {
            *a4 = 0;
          }
          v13 = 0;
          if ( a3 )
            *a3 = v16;
          return v13;
        }
        v11 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          return 1009;
        }
        v12 = 191;
      }
    }
    else
    {
      v11 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        return 1009;
      }
      v12 = 189;
    }
    WPP_SF_(*((_QWORD *)v11 + 2), v12, &WPP_b5057cf466d13e046d0380d31f78638c_Traceguids);
    return 1009;
  }
  if ( v7 != (CMapDeviceId *)&WPP_GLOBAL_Control && (*((_BYTE *)v7 + 28) & 4) != 0 && *((_BYTE *)v7 + 25) >= 2u )
    WPP_SF_(*((_QWORD *)v7 + 2), 188, &WPP_b5057cf466d13e046d0380d31f78638c_Traceguids);
  return 111;
}

```

## disassembly

```asm
0x140006d38  mov     [rsp+arg_0], rbx
0x140006d3d  push    rbp
0x140006d3e  push    rsi
0x140006d3f  push    rdi
0x140006d40  push    r12
0x140006d42  push    r15
0x140006d44  sub     rsp, 250h
0x140006d4b  mov     rax, cs:__security_cookie
0x140006d52  xor     rax, rsp
0x140006d55  mov     [rsp+278h+var_38], rax
0x140006d5d  mov     rsi, r8
0x140006d60  lea     rcx, [rsp+278h+String1]; void *
0x140006d65  mov     rdi, rdx
0x140006d68  mov     r8d, 208h; Size
0x140006d6e  xor     edx, edx; Val
0x140006d70  mov     rbx, r9
0x140006d73  call    memset_0
0x140006d78  xor     ebp, ebp
0x140006d7a  mov     [rsp+278h+var_250], rbp
0x140006d7f  mov     rcx, cs:WPP_GLOBAL_Control
0x140006d86  lea     r12, WPP_GLOBAL_Control
0x140006d8d  lea     r15, WPP_b5057cf466d13e046d0380d31f78638c_Traceguids
0x140006d94  cmp     rcx, r12
0x140006d97  jz      short loc_140006DBD
0x140006d99  test    byte ptr [rcx+1Ch], 4
0x140006d9d  jz      short loc_140006DBD
0x140006d9f  cmp     byte ptr [rcx+19h], 5
0x140006da3  jb      short loc_140006DBD
0x140006da5  mov     rcx, [rcx+10h]
0x140006da9  mov     edx, 0BBh
0x140006dae  mov     r8, r15
0x140006db1  call    WPP_SF_
0x140006db6  mov     rcx, cs:WPP_GLOBAL_Control
0x140006dbd  or      rax, 0FFFFFFFFFFFFFFFFh
0x140006dc1  inc     rax
0x140006dc4  cmp     [rdi+rax*2], bp
0x140006dc8  jnz     short loc_140006DC1
0x140006dca  cmp     rax, 104h
0x140006dd0  jb      short loc_140006DFE
0x140006dd2  cmp     rcx, r12
0x140006dd5  jz      short loc_140006DF4
0x140006dd7  test    byte ptr [rcx+1Ch], 4
0x140006ddb  jz      short loc_140006DF4
0x140006ddd  cmp     byte ptr [rcx+19h], 2
0x140006de1  jb      short loc_140006DF4
0x140006de3  mov     rcx, [rcx+10h]
0x140006de7  mov     edx, 0BCh
0x140006dec  mov     r8, r15
0x140006def  call    WPP_SF_
0x140006df4  mov     eax, 6Fh ; 'o'
0x140006df9  jmp     loc_140006F86
0x140006dfe  mov     edx, 24h ; '$'; Ch
0x140006e03  mov     rcx, rdi; Str
0x140006e06  call    cs:__imp_wcschr
0x140006e0d  nop     dword ptr [rax+rax+00h]
0x140006e12  test    rax, rax
0x140006e15  jnz     short loc_140006E4A
0x140006e17  mov     rcx, cs:WPP_GLOBAL_Control
0x140006e1e  cmp     rcx, r12
0x140006e21  jz      short loc_140006E40
0x140006e23  test    byte ptr [rcx+1Ch], 4
0x140006e27  jz      short loc_140006E40
0x140006e29  cmp     byte ptr [rcx+19h], 2
0x140006e2d  jb      short loc_140006E40
0x140006e2f  mov     edx, 0BDh
0x140006e34  mov     rcx, [rcx+10h]
0x140006e38  mov     r8, r15
0x140006e3b  call    WPP_SF_
0x140006e40  mov     ebx, 3F1h
0x140006e45  jmp     loc_140006F84
0x140006e4a  mov     edx, 24h ; '$'; Ch
0x140006e4f  lea     rcx, [rax+2]; Str
0x140006e53  call    cs:__imp_wcschr
0x140006e5a  nop     dword ptr [rax+rax+00h]
0x140006e5f  test    rax, rax
0x140006e62  jz      short loc_140006E83
0x140006e64  mov     rcx, cs:WPP_GLOBAL_Control
0x140006e6b  cmp     rcx, r12
0x140006e6e  jz      short loc_140006E40
0x140006e70  test    byte ptr [rcx+1Ch], 4
0x140006e74  jz      short loc_140006E40
0x140006e76  cmp     byte ptr [rcx+19h], 2
0x140006e7a  jb      short loc_140006E40
0x140006e7c  mov     edx, 0BEh
0x140006e81  jmp     short loc_140006E34
0x140006e83  lea     r9, [rsp+278h+var_250]
0x140006e88  mov     rcx, rdi; Buffer
0x140006e8b  lea     r8, [rsp+278h+String1]
0x140006e90  lea     rdx, aI64x; "%[^$]$%I64x"
0x140006e97  call    cs:__imp_swscanf
0x140006e9e  nop     dword ptr [rax+rax+00h]
0x140006ea3  cmp     eax, 2
0x140006ea6  jz      short loc_140006ECA
0x140006ea8  mov     rcx, cs:WPP_GLOBAL_Control
0x140006eaf  cmp     rcx, r12
0x140006eb2  jz      short loc_140006E40
0x140006eb4  test    byte ptr [rcx+1Ch], 4
0x140006eb8  jz      short loc_140006E40
0x140006eba  cmp     byte ptr [rcx+19h], 2
0x140006ebe  jb      short loc_140006E40
0x140006ec0  mov     edx, 0BFh
0x140006ec5  jmp     loc_140006E34
0x140006eca  mov     r8d, 0Bh; MaxCount
0x140006ed0  lea     rdx, aUnassigned; "UnAssigned"
0x140006ed7  lea     rcx, [rsp+278h+String1]; String1
0x140006edc  call    cs:__imp__wcsnicmp
0x140006ee3  nop     dword ptr [rax+rax+00h]
0x140006ee8  test    eax, eax
0x140006eea  jnz     short loc_140006EFA
0x140006eec  test    rbx, rbx
0x140006eef  jz      loc_140006F75
0x140006ef5  mov     [rbx], rbp
0x140006ef8  jmp     short loc_140006F75
0x140006efa  lea     rdx, [rsp+278h+Sid]; Sid
0x140006eff  mov     [rsp+278h+Sid], rbp
0x140006f04  lea     rcx, [rsp+278h+String1]; StringSid
0x140006f09  call    cs:__imp_ConvertStringSidToSidW
0x140006f10  nop     dword ptr [rax+rax+00h]
0x140006f15  test    eax, eax
0x140006f17  jnz     short loc_140006F55
0x140006f19  call    cs:__imp_GetLastError
0x140006f20  nop     dword ptr [rax+rax+00h]
0x140006f25  mov     ebx, eax
0x140006f27  mov     rcx, cs:WPP_GLOBAL_Control
0x140006f2e  cmp     rcx, r12
0x140006f31  jz      short loc_140006F84
0x140006f33  test    byte ptr [rcx+1Ch], 4
0x140006f37  jz      short loc_140006F84
0x140006f39  cmp     byte ptr [rcx+19h], 2
0x140006f3d  jb      short loc_140006F84
0x140006f3f  mov     rcx, [rcx+10h]
0x140006f43  mov     edx, 0C0h
0x140006f48  mov     r9d, eax
0x140006f4b  mov     r8, r15
0x140006f4e  call    WPP_SF_d
0x140006f53  jmp     short loc_140006F84
0x140006f55  test    rbx, rbx
0x140006f58  jz      short loc_140006F64
0x140006f5a  mov     rax, [rsp+278h+Sid]
0x140006f5f  mov     [rbx], rax
0x140006f62  jmp     short loc_140006F75
0x140006f64  mov     rcx, [rsp+278h+Sid]; hMem
0x140006f69  call    cs:__imp_LocalFree
0x140006f70  nop     dword ptr [rax+rax+00h]
0x140006f75  mov     ebx, ebp
0x140006f77  test    rsi, rsi
0x140006f7a  jz      short loc_140006F84
0x140006f7c  mov     rax, [rsp+278h+var_250]
0x140006f81  mov     [rsi], rax
0x140006f84  mov     eax, ebx
0x140006f86  mov     rcx, [rsp+278h+var_38]
0x140006f8e  xor     rcx, rsp; StackCookie
0x140006f91  call    __security_check_cookie
0x140006f96  mov     rbx, [rsp+278h+arg_0]
0x140006f9e  add     rsp, 250h
0x140006fa5  pop     r15
0x140006fa7  pop     r12
0x140006fa9  pop     rdi
0x140006faa  pop     rsi
0x140006fab  pop     rbp
0x140006fac  retn
```
