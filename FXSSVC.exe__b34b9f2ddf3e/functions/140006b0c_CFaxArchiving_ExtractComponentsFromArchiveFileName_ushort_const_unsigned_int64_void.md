# CFaxArchiving::ExtractComponentsFromArchiveFileName(ushort const *,unsigned __int64 *,void * *)

- ea: `0x140006b0c`
- end: `0x140006d53`
- name: `?ExtractComponentsFromArchiveFileName@CFaxArchiving@@QEAAKPEBGPEA_KPEAPEAX@Z`
- size: `583`
- prototype: `__int64 __fastcall(CFaxArchiving *this, const unsigned __int16 *, unsigned __int64 *, void **)`
- caller_count: `6`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140005f7c`
- `0x140008f3c`
- `0x140009db0`
- `0x140012e20`
- `0x140014b18`
- `0x14001cb80`

## callees

- `0x140002c43`
- `0x140004b30`
- `0x140004b58`
- `0x140006b0c`
- `0x1400818b0`

## import_xrefs

- `ADVAPI32!ConvertStringSidToSidW` at `0x140006cc1`
- `ADVAPI32!ConvertStringSidToSidW` at `0x140006cc1`
- `KERNEL32!GetLastError` at `0x140006ccb`
- `KERNEL32!GetLastError` at `0x140006ccb`
- `KERNEL32!LocalFree` at `0x140006d15`
- `KERNEL32!LocalFree` at `0x140006d15`
- `msvcrt!_wcsnicmp` at `0x140006c9e`
- `msvcrt!_wcsnicmp` at `0x140006c9e`
- `msvcrt!swscanf` at `0x140006c5f`
- `msvcrt!swscanf` at `0x140006c5f`
- `msvcrt!wcschr` at `0x140006bda`
- `msvcrt!wcschr` at `0x140006c21`
- `msvcrt!wcschr` at `0x140006bda`
- `msvcrt!wcschr` at `0x140006c21`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
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
0x140006b0c  mov     [rsp+arg_0], rbx
0x140006b11  push    rbp
0x140006b12  push    rsi
0x140006b13  push    rdi
0x140006b14  push    r12
0x140006b16  push    r15
0x140006b18  sub     rsp, 250h
0x140006b1f  mov     rax, cs:__security_cookie
0x140006b26  xor     rax, rsp
0x140006b29  mov     [rsp+278h+var_38], rax
0x140006b31  mov     rsi, r8
0x140006b34  lea     rcx, [rsp+278h+String1]; void *
0x140006b39  mov     rdi, rdx
0x140006b3c  mov     r8d, 208h; Size
0x140006b42  xor     edx, edx; Val
0x140006b44  mov     rbx, r9
0x140006b47  call    memset_0
0x140006b4c  xor     ebp, ebp
0x140006b4e  mov     [rsp+278h+var_250], rbp
0x140006b53  mov     rcx, cs:WPP_GLOBAL_Control
0x140006b5a  lea     r12, WPP_GLOBAL_Control
0x140006b61  lea     r15, WPP_b5057cf466d13e046d0380d31f78638c_Traceguids
0x140006b68  cmp     rcx, r12
0x140006b6b  jz      short loc_140006B91
0x140006b6d  test    byte ptr [rcx+1Ch], 4
0x140006b71  jz      short loc_140006B91
0x140006b73  cmp     byte ptr [rcx+19h], 5
0x140006b77  jb      short loc_140006B91
0x140006b79  mov     rcx, [rcx+10h]
0x140006b7d  mov     edx, 0BBh
0x140006b82  mov     r8, r15
0x140006b85  call    WPP_SF_
0x140006b8a  mov     rcx, cs:WPP_GLOBAL_Control
0x140006b91  or      rax, 0FFFFFFFFFFFFFFFFh
0x140006b95  inc     rax
0x140006b98  cmp     [rdi+rax*2], bp
0x140006b9c  jnz     short loc_140006B95
0x140006b9e  cmp     rax, 104h
0x140006ba4  jb      short loc_140006BD2
0x140006ba6  cmp     rcx, r12
0x140006ba9  jz      short loc_140006BC8
0x140006bab  test    byte ptr [rcx+1Ch], 4
0x140006baf  jz      short loc_140006BC8
0x140006bb1  cmp     byte ptr [rcx+19h], 2
0x140006bb5  jb      short loc_140006BC8
0x140006bb7  mov     rcx, [rcx+10h]
0x140006bbb  mov     edx, 0BCh
0x140006bc0  mov     r8, r15
0x140006bc3  call    WPP_SF_
0x140006bc8  mov     eax, 6Fh ; 'o'
0x140006bcd  jmp     loc_140006D2C
0x140006bd2  mov     edx, 24h ; '$'; Ch
0x140006bd7  mov     rcx, rdi; Str
0x140006bda  call    cs:__imp_wcschr
0x140006be0  test    rax, rax
0x140006be3  jnz     short loc_140006C18
0x140006be5  mov     rcx, cs:WPP_GLOBAL_Control
0x140006bec  cmp     rcx, r12
0x140006bef  jz      short loc_140006C0E
0x140006bf1  test    byte ptr [rcx+1Ch], 4
0x140006bf5  jz      short loc_140006C0E
0x140006bf7  cmp     byte ptr [rcx+19h], 2
0x140006bfb  jb      short loc_140006C0E
0x140006bfd  mov     edx, 0BDh
0x140006c02  mov     rcx, [rcx+10h]
0x140006c06  mov     r8, r15
0x140006c09  call    WPP_SF_
0x140006c0e  mov     ebx, 3F1h
0x140006c13  jmp     loc_140006D2A
0x140006c18  mov     edx, 24h ; '$'; Ch
0x140006c1d  lea     rcx, [rax+2]; Str
0x140006c21  call    cs:__imp_wcschr
0x140006c27  test    rax, rax
0x140006c2a  jz      short loc_140006C4B
0x140006c2c  mov     rcx, cs:WPP_GLOBAL_Control
0x140006c33  cmp     rcx, r12
0x140006c36  jz      short loc_140006C0E
0x140006c38  test    byte ptr [rcx+1Ch], 4
0x140006c3c  jz      short loc_140006C0E
0x140006c3e  cmp     byte ptr [rcx+19h], 2
0x140006c42  jb      short loc_140006C0E
0x140006c44  mov     edx, 0BEh
0x140006c49  jmp     short loc_140006C02
0x140006c4b  lea     r9, [rsp+278h+var_250]
0x140006c50  mov     rcx, rdi; Buffer
0x140006c53  lea     r8, [rsp+278h+String1]
0x140006c58  lea     rdx, aI64x; "%[^$]$%I64x"
0x140006c5f  call    cs:__imp_swscanf
0x140006c65  cmp     eax, 2
0x140006c68  jz      short loc_140006C8C
0x140006c6a  mov     rcx, cs:WPP_GLOBAL_Control
0x140006c71  cmp     rcx, r12
0x140006c74  jz      short loc_140006C0E
0x140006c76  test    byte ptr [rcx+1Ch], 4
0x140006c7a  jz      short loc_140006C0E
0x140006c7c  cmp     byte ptr [rcx+19h], 2
0x140006c80  jb      short loc_140006C0E
0x140006c82  mov     edx, 0BFh
0x140006c87  jmp     loc_140006C02
0x140006c8c  mov     r8d, 0Bh; MaxCount
0x140006c92  lea     rdx, aUnassigned; "UnAssigned"
0x140006c99  lea     rcx, [rsp+278h+String1]; String1
0x140006c9e  call    cs:__imp__wcsnicmp
0x140006ca4  test    eax, eax
0x140006ca6  jnz     short loc_140006CB2
0x140006ca8  test    rbx, rbx
0x140006cab  jz      short loc_140006D1B
0x140006cad  mov     [rbx], rbp
0x140006cb0  jmp     short loc_140006D1B
0x140006cb2  lea     rdx, [rsp+278h+Sid]; Sid
0x140006cb7  mov     [rsp+278h+Sid], rbp
0x140006cbc  lea     rcx, [rsp+278h+String1]; StringSid
0x140006cc1  call    cs:__imp_ConvertStringSidToSidW
0x140006cc7  test    eax, eax
0x140006cc9  jnz     short loc_140006D01
0x140006ccb  call    cs:__imp_GetLastError
0x140006cd1  mov     ebx, eax
0x140006cd3  mov     rcx, cs:WPP_GLOBAL_Control
0x140006cda  cmp     rcx, r12
0x140006cdd  jz      short loc_140006D2A
0x140006cdf  test    byte ptr [rcx+1Ch], 4
0x140006ce3  jz      short loc_140006D2A
0x140006ce5  cmp     byte ptr [rcx+19h], 2
0x140006ce9  jb      short loc_140006D2A
0x140006ceb  mov     rcx, [rcx+10h]
0x140006cef  mov     edx, 0C0h
0x140006cf4  mov     r9d, eax
0x140006cf7  mov     r8, r15
0x140006cfa  call    WPP_SF_d
0x140006cff  jmp     short loc_140006D2A
0x140006d01  test    rbx, rbx
0x140006d04  jz      short loc_140006D10
0x140006d06  mov     rax, [rsp+278h+Sid]
0x140006d0b  mov     [rbx], rax
0x140006d0e  jmp     short loc_140006D1B
0x140006d10  mov     rcx, [rsp+278h+Sid]; hMem
0x140006d15  call    cs:__imp_LocalFree
0x140006d1b  mov     ebx, ebp
0x140006d1d  test    rsi, rsi
0x140006d20  jz      short loc_140006D2A
0x140006d22  mov     rax, [rsp+278h+var_250]
0x140006d27  mov     [rsi], rax
0x140006d2a  mov     eax, ebx
0x140006d2c  mov     rcx, [rsp+278h+var_38]
0x140006d34  xor     rcx, rsp; StackCookie
0x140006d37  call    __security_check_cookie
0x140006d3c  mov     rbx, [rsp+278h+arg_0]
0x140006d44  add     rsp, 250h
0x140006d4b  pop     r15
0x140006d4d  pop     r12
0x140006d4f  pop     rdi
0x140006d50  pop     rsi
0x140006d51  pop     rbp
0x140006d52  retn
```
