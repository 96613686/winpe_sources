# GetMsiComponentAndProduct

- ea: `0x180002f08`
- end: `0x18000318d`
- name: `GetMsiComponentAndProduct`
- size: `645`
- prototype: `__int64 __usercall@<rax>(HMODULE hModule@<rcx>, __int64, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `reparse_path, installer_update, broker_com_uri`

## callers

- `0x180003ac8`

## callees

- `0x180002590`
- `0x180002f08`
- `0x180007040`
- `0x180008010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x180003079`
- `msvcrt!_wcsicmp` at `0x180003079`
- `KERNEL32!GetProcAddress` at `0x180002f77`
- `KERNEL32!GetProcAddress` at `0x180002fae`
- `KERNEL32!GetProcAddress` at `0x180002fce`
- `KERNEL32!GetProcAddress` at `0x180002fee`
- `KERNEL32!GetProcAddress` at `0x180002f77`
- `KERNEL32!GetProcAddress` at `0x180002fae`
- `KERNEL32!GetProcAddress` at `0x180002fce`
- `KERNEL32!GetProcAddress` at `0x180002fee`

## string_xrefs

- `0x18000315b`: `MSI-COFIRE ERROR: %s:%d - hr = 0x%08X\n`
- `0x180002f6b`: `MsiEnumComponentsW`
- `0x180003154`: `GetMsiComponentAndProduct`
- `0x180002fa4`: `MsiEnumClientsW`
- `0x180002fc4`: `MsiGetComponentPathW`
- `0x180002fe4`: `MsiGetProductInfoW`
- `0x1800030a4`: `InstalledProductName`

## pseudocode

```c
__int64 __fastcall GetMsiComponentAndProduct(
        HMODULE hModule,
        wchar_t *a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        __int64 a7,
        __int64 a8)
{
  int v11; // esi
  int v12; // r9d
  unsigned int v13; // ebx
  FARPROC v14; // r15
  FARPROC v15; // r12
  FARPROC v16; // rbp
  int v17; // eax
  unsigned int i; // edi
  int v19; // eax
  int v20; // r9d
  int v21; // eax
  int v23; // [rsp+30h] [rbp-2A8h] BYREF
  wchar_t *String1; // [rsp+38h] [rbp-2A0h]
  FARPROC ProcAddress; // [rsp+40h] [rbp-298h]
  __int64 v26; // [rsp+48h] [rbp-290h]
  __int64 v27; // [rsp+50h] [rbp-288h]
  __int64 v28; // [rsp+58h] [rbp-280h]
  __int64 v29; // [rsp+60h] [rbp-278h]
  wchar_t String2[264]; // [rsp+70h] [rbp-268h] BYREF

  v27 = a5;
  v26 = a6;
  v29 = a7;
  String1 = a2;
  v28 = a8;
  v11 = 0;
  ProcAddress = GetProcAddress(hModule, "MsiEnumComponentsW");
  if ( ProcAddress )
  {
    v14 = GetProcAddress(hModule, "MsiEnumClientsW");
    if ( v14 )
    {
      v15 = GetProcAddress(hModule, "MsiGetComponentPathW");
      if ( v15 )
      {
        v16 = GetProcAddress(hModule, "MsiGetProductInfoW");
        if ( v16 )
        {
          v17 = ((__int64 (__fastcall *)(_QWORD, __int64))ProcAddress)(0, a4);
LABEL_11:
          if ( v17 )
          {
            v13 = -2147023728;
            if ( v17 == 259 )
              return v13;
            if ( v17 > 0 )
              v13 = (unsigned __int16)v17 | 0x80070000;
            else
              v13 = v17;
            v20 = 876;
          }
          else
          {
            for ( i = 0; ; ++i )
            {
              v13 = ((__int64 (__fastcall *)(__int64, _QWORD, __int64))v14)(a4, i, a3);
              if ( v13 )
              {
                if ( v13 == 259 )
                {
                  v17 = ((__int64 (__fastcall *)(_QWORD, __int64))ProcAddress)((unsigned int)++v11, a4);
                  goto LABEL_11;
                }
                if ( (int)v13 > 0 )
                  v13 = (unsigned __int16)v13 | 0x80070000;
                v20 = 869;
                goto LABEL_39;
              }
              if ( g_bDmCanceled )
                return 2147943568LL;
              v23 = 260;
              if ( ((unsigned int (__fastcall *)(__int64, __int64, wchar_t *, int *))v15)(a3, a4, String2, &v23) == 3
                && String2[0]
                && !_wcsicmp(String1, String2) )
              {
                break;
              }
            }
            v19 = ((__int64 (__fastcall *)(__int64, const wchar_t *, __int64, __int64))v16)(
                    a3,
                    L"InstalledProductName",
                    v27,
                    v26);
            v13 = v19;
            if ( v19 )
            {
              if ( v19 > 0 )
                v13 = (unsigned __int16)v19 | 0x80070000;
              v20 = 851;
            }
            else
            {
              v21 = ((__int64 (__fastcall *)(__int64, const wchar_t *, __int64, __int64))v16)(
                      a3,
                      L"VersionString",
                      v29,
                      v28);
              v13 = v21;
              if ( !v21 )
                return 0;
              if ( v21 > 0 )
                v13 = (unsigned __int16)v21 | 0x80070000;
              v20 = 859;
            }
          }
LABEL_39:
          DebugPrint(0, "MSI-COFIRE ERROR: %s:%d - hr = 0x%08X\n", "GetMsiComponentAndProduct", v20, v13);
          return v13;
        }
        v12 = 816;
      }
      else
      {
        v12 = 812;
      }
    }
    else
    {
      v12 = 808;
    }
  }
  else
  {
    v12 = 804;
  }
  v13 = -2147467259;
  DebugPrint(0, "MSI-COFIRE ERROR: %s:%d - hr = 0x%08X\n", "GetMsiComponentAndProduct", v12, -2147467259);
  return v13;
}

```

## disassembly

```asm
0x180002f08  push    rbx
0x180002f0a  push    rbp
0x180002f0b  push    rsi
0x180002f0c  push    rdi
0x180002f0d  push    r12
0x180002f0f  push    r13
0x180002f11  push    r14
0x180002f13  push    r15
0x180002f15  sub     rsp, 298h
0x180002f1c  mov     rax, cs:__security_cookie
0x180002f23  xor     rax, rsp
0x180002f26  mov     [rsp+2D8h+var_58], rax
0x180002f2e  mov     rax, [rsp+2D8h+arg_20]
0x180002f36  mov     r13, r9
0x180002f39  mov     [rsp+2D8h+var_288], rax
0x180002f3e  mov     r14, r8
0x180002f41  mov     rax, [rsp+2D8h+arg_28]
0x180002f49  mov     rbx, rcx
0x180002f4c  mov     [rsp+2D8h+var_290], rax
0x180002f51  mov     rax, [rsp+2D8h+arg_30]
0x180002f59  mov     [rsp+2D8h+var_278], rax
0x180002f5e  mov     rax, [rsp+2D8h+arg_38]
0x180002f66  mov     [rsp+2D8h+String1], rdx
0x180002f6b  lea     rdx, ProcName; "MsiEnumComponentsW"
0x180002f72  mov     [rsp+2D8h+var_280], rax
0x180002f77  call    cs:__imp_GetProcAddress
0x180002f7d  xor     esi, esi
0x180002f7f  mov     [rsp+2D8h+var_298], rax
0x180002f84  mov     rdi, rax
0x180002f87  test    rax, rax
0x180002f8a  jnz     short loc_180002FA4
0x180002f8c  mov     r9d, 324h
0x180002f92  mov     eax, 80004005h
0x180002f97  xor     ecx, ecx
0x180002f99  mov     [rsp+2D8h+var_2B8], eax
0x180002f9d  mov     ebx, eax
0x180002f9f  jmp     loc_180003154
0x180002fa4  lea     rdx, aMsienumclients; "MsiEnumClientsW"
0x180002fab  mov     rcx, rbx; hModule
0x180002fae  call    cs:__imp_GetProcAddress
0x180002fb4  mov     r15, rax
0x180002fb7  test    rax, rax
0x180002fba  jnz     short loc_180002FC4
0x180002fbc  mov     r9d, 328h
0x180002fc2  jmp     short loc_180002F92
0x180002fc4  lea     rdx, aMsigetcomponen; "MsiGetComponentPathW"
0x180002fcb  mov     rcx, rbx; hModule
0x180002fce  call    cs:__imp_GetProcAddress
0x180002fd4  mov     r12, rax
0x180002fd7  test    rax, rax
0x180002fda  jnz     short loc_180002FE4
0x180002fdc  mov     r9d, 32Ch
0x180002fe2  jmp     short loc_180002F92
0x180002fe4  lea     rdx, aMsigetproducti; "MsiGetProductInfoW"
0x180002feb  mov     rcx, rbx; hModule
0x180002fee  call    cs:__imp_GetProcAddress
0x180002ff4  mov     rbp, rax
0x180002ff7  test    rax, rax
0x180002ffa  jnz     short loc_180003004
0x180002ffc  mov     r9d, 330h
0x180003002  jmp     short loc_180002F92
0x180003004  mov     rdx, r13
0x180003007  mov     ecx, esi
0x180003009  mov     rax, rdi
0x18000300c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003011  xor     ecx, ecx; Level
0x180003013  test    eax, eax
0x180003015  jnz     loc_18000312D
0x18000301b  mov     edi, ecx
0x18000301d  mov     r8, r14
0x180003020  mov     edx, edi
0x180003022  mov     rcx, r13
0x180003025  mov     rax, r15
0x180003028  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000302d  mov     ebx, eax
0x18000302f  xor     eax, eax
0x180003031  test    ebx, ebx
0x180003033  jnz     short loc_180003087
0x180003035  cmp     cs:g_bDmCanceled, eax
0x18000303b  jnz     loc_180003111
0x180003041  lea     r9, [rsp+2D8h+var_2A8]
0x180003046  mov     [rsp+2D8h+var_2A8], 104h
0x18000304e  lea     r8, [rsp+2D8h+String2]
0x180003053  mov     rdx, r13
0x180003056  mov     rcx, r14
0x180003059  mov     rax, r12
0x18000305c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003061  cmp     eax, 3
0x180003064  jnz     short loc_180003083
0x180003066  xor     ebx, ebx
0x180003068  cmp     [rsp+2D8h+String2], bx
0x18000306d  jz      short loc_180003083
0x18000306f  mov     rcx, [rsp+2D8h+String1]; String1
0x180003074  lea     rdx, [rsp+2D8h+String2]; String2
0x180003079  call    cs:__imp__wcsicmp
0x18000307f  test    eax, eax
0x180003081  jz      short loc_18000309F
0x180003083  inc     edi
0x180003085  jmp     short loc_18000301D
0x180003087  cmp     ebx, 103h
0x18000308d  jnz     loc_180003118
0x180003093  mov     rdi, [rsp+2D8h+var_298]
0x180003098  inc     esi
0x18000309a  jmp     loc_180003004
0x18000309f  mov     r9, [rsp+2D8h+var_290]
0x1800030a4  lea     rdx, aInstalledprodu; "InstalledProductName"
0x1800030ab  mov     r8, [rsp+2D8h+var_288]
0x1800030b0  mov     rcx, r14
0x1800030b3  mov     rax, rbp
0x1800030b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800030bb  xor     edi, edi
0x1800030bd  mov     ebx, eax
0x1800030bf  test    eax, eax
0x1800030c1  jz      short loc_1800030D8
0x1800030c3  jle     short loc_1800030CE
0x1800030c5  movzx   ebx, ax
0x1800030c8  or      ebx, 80070000h
0x1800030ce  mov     r9d, 353h
0x1800030d4  xor     ecx, ecx
0x1800030d6  jmp     short loc_180003150
0x1800030d8  mov     r9, [rsp+2D8h+var_280]
0x1800030dd  lea     rdx, aVersionstring; "VersionString"
0x1800030e4  mov     r8, [rsp+2D8h+var_278]
0x1800030e9  mov     rcx, r14
0x1800030ec  mov     rax, rbp
0x1800030ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800030f4  mov     ebx, eax
0x1800030f6  test    eax, eax
0x1800030f8  jz      short loc_18000310D
0x1800030fa  jle     short loc_180003105
0x1800030fc  movzx   ebx, ax
0x1800030ff  or      ebx, 80070000h
0x180003105  mov     r9d, 35Bh
0x18000310b  jmp     short loc_1800030D4
0x18000310d  mov     ebx, edi
0x18000310f  jmp     short loc_180003167
0x180003111  mov     eax, 80070490h
0x180003116  jmp     short loc_180003169
0x180003118  test    ebx, ebx
0x18000311a  jle     short loc_180003125
0x18000311c  movzx   ebx, bx
0x18000311f  or      ebx, 80070000h
0x180003125  mov     r9d, 365h
0x18000312b  jmp     short loc_1800030D4
0x18000312d  mov     ebx, 80070490h
0x180003132  cmp     eax, 103h
0x180003137  jz      short loc_180003167
0x180003139  test    eax, eax
0x18000313b  jg      short loc_180003141
0x18000313d  mov     ebx, eax
0x18000313f  jmp     short loc_18000314A
0x180003141  movzx   ebx, ax
0x180003144  or      ebx, 80070000h
0x18000314a  mov     r9d, 36Ch
0x180003150  mov     [rsp+2D8h+var_2B8], ebx
0x180003154  lea     r8, aGetmsicomponen; "GetMsiComponentAndProduct"
0x18000315b  lea     rdx, aMsiCofireError; "MSI-COFIRE ERROR: %s:%d - hr = 0x%08X\n"
0x180003162  call    ?DebugPrint@@YAXKPEBDZZ; DebugPrint(ulong,char const *,...)
0x180003167  mov     eax, ebx
0x180003169  mov     rcx, [rsp+2D8h+var_58]
0x180003171  xor     rcx, rsp; StackCookie
0x180003174  call    __security_check_cookie
0x180003179  add     rsp, 298h
0x180003180  pop     r15
0x180003182  pop     r14
0x180003184  pop     r13
0x180003186  pop     r12
0x180003188  pop     rdi
0x180003189  pop     rsi
0x18000318a  pop     rbp
0x18000318b  pop     rbx
0x18000318c  retn
```
