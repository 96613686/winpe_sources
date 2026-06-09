# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x18000dcdc`
- end: `0x18000dfb9`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `733`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `2`
- callee_count: `6`
- tags: ``

## callers

- `0x18000d82c`
- `0x18000daa0`

## callees

- `0x18000dcdc`
- `0x18000dfc0`
- `0x18000e124`
- `0x18002477c`
- `0x180028a70`
- `0x18002a030`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000dd9e`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000de10`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000dd9e`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000de10`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000de6d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000de6d`

## pseudocode

```c
__int64 __fastcall wil::details_abi::SemaphoreValue::TryGetValueInternal(
        WCHAR *a1,
        __int64 a2,
        unsigned __int64 *a3,
        bool *a4)
{
  WCHAR *v4; // rax
  __int64 v5; // r14
  __int64 v6; // r9
  __int64 v7; // rdx
  bool v9; // zf
  WCHAR *v10; // rcx
  __int64 v11; // rdx
  WCHAR *v12; // rax
  __int64 v13; // r8
  wil::details *v14; // rax
  wil::details *v15; // rdi
  int ValueFromSemaphore; // eax
  unsigned int LastError; // esi
  __int64 v18; // rdx
  WCHAR *v19; // rax
  __int64 v20; // r8
  wil::details *v21; // rax
  const char *v22; // r9
  wil::details *v23; // rbx
  void *v24; // rdx
  const char *v26; // r9
  int v27; // eax
  void *v28; // rdx
  void *v29; // rdx
  const wchar_t *v30; // r9
  __int64 v31; // rcx
  WCHAR *v32; // rdx
  __int64 v33; // rax
  WCHAR *v34; // rcx
  WCHAR *v35; // rax
  const unsigned __int16 *v36; // rcx
  __int64 v37; // rbx
  WCHAR *v38; // rdx
  void *v39; // rdx
  int v40; // [rsp+20h] [rbp-E0h] BYREF
  int v41[3]; // [rsp+24h] [rbp-DCh] BYREF
  WCHAR Name[264]; // [rsp+30h] [rbp-D0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+178h]

  v4 = Name;
  v5 = 2147483646;
  *a3 = 0;
  v6 = 2147483646;
  v7 = 260;
  do
  {
    if ( !v6 )
      break;
    if ( !*a1 )
      break;
    *v4++ = *a1++;
    --v6;
    --v7;
  }
  while ( v7 );
  v9 = v7 == 0;
  v10 = v4 - 1;
  v11 = 260;
  if ( !v9 )
    v10 = v4;
  v12 = Name;
  *v10 = 0;
  do
  {
    if ( !*v12 )
      break;
    ++v12;
    --v11;
  }
  while ( v11 );
  v13 = (260 - v11) & -(__int64)(v11 != 0);
  if ( v11 )
  {
    v30 = L"_p0";
    v31 = 2147483646;
    v32 = &Name[v13];
    v33 = 260 - v13;
    if ( v13 != 260 )
    {
      do
      {
        if ( !v31 )
          break;
        if ( !*v30 )
          break;
        *v32++ = *v30++;
        --v31;
        --v33;
      }
      while ( v33 );
    }
    v34 = v32 - 1;
    if ( v33 )
      v34 = v32;
    *v34 = 0;
  }
  v14 = (wil::details *)OpenSemaphoreW(0x1F0003u, 0, Name);
  v15 = v14;
  if ( v14 )
  {
    v41[0] = 0;
    v40 = 0;
    ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v14, v41);
    LastError = ValueFromSemaphore;
    if ( ValueFromSemaphore < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xD6,
        (unsigned int)"wil",
        (const char *)(unsigned int)ValueFromSemaphore,
        v40);
      goto LABEL_19;
    }
    v18 = 260;
    v19 = Name;
    do
    {
      if ( !*v19 )
        break;
      ++v19;
      --v18;
    }
    while ( v18 );
    v20 = (260 - v18) & -(__int64)(v18 != 0);
    if ( v18 )
    {
      v35 = &Name[v20];
      v36 = L"h";
      v37 = 260 - v20;
      if ( 260 != v20 )
      {
        do
        {
          if ( !v5 )
            break;
          if ( !*v36 )
            break;
          *v35++ = *v36++;
          --v5;
          --v37;
        }
        while ( v37 );
      }
      v38 = v35 - 1;
      if ( v37 )
        v38 = v35;
      *v38 = 0;
    }
    v21 = (wil::details *)OpenSemaphoreW(0x1F0003u, 0, Name);
    v23 = v21;
    if ( !v21 )
    {
      LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xDC, (unsigned int)"wil", v22);
LABEL_19:
      wil::details::CloseHandle(v15, v24);
      return LastError;
    }
    v27 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v21, &v40);
    LastError = v27;
    if ( v27 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xDE,
        (unsigned int)"wil",
        (const char *)(unsigned int)v27,
        v40);
      wil::details::CloseHandle(v23, v39);
      goto LABEL_19;
    }
    wil::details::CloseHandle(v23, v28);
    *a3 = v41[0] | (unsigned __int64)((__int64)v40 << 31);
    wil::details::CloseHandle(v15, v29);
  }
  else if ( GetLastError() != 2 )
  {
    return wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xD0, (unsigned int)"wil", v26);
  }
  return 0;
}

```

## disassembly

```asm
0x18000dcdc  mov     [rsp-8+arg_0], rbx
0x18000dce1  mov     [rsp-8+arg_8], rsi
0x18000dce6  push    rbp
0x18000dce7  push    rdi
0x18000dce8  push    r12
0x18000dcea  push    r14
0x18000dcec  push    r15
0x18000dcee  lea     rbp, [rsp-150h]
0x18000dcf6  sub     rsp, 250h
0x18000dcfd  mov     rax, cs:__security_cookie
0x18000dd04  xor     rax, rsp
0x18000dd07  mov     [rbp+170h+var_30], rax
0x18000dd0e  xor     r12d, r12d
0x18000dd11  lea     rax, [rsp+270h+Name]
0x18000dd16  mov     r14d, 7FFFFFFEh
0x18000dd1c  mov     [r8], r12
0x18000dd1f  mov     ebx, 104h
0x18000dd24  mov     r9d, r14d
0x18000dd27  mov     edx, ebx
0x18000dd29  mov     r15, r8
0x18000dd2c  test    r9, r9
0x18000dd2f  jz      short loc_18000DD50
0x18000dd31  movzx   r8d, word ptr [rcx]
0x18000dd35  test    r8w, r8w
0x18000dd39  jz      short loc_18000DD50
0x18000dd3b  mov     [rax], r8w
0x18000dd3f  add     rcx, 2
0x18000dd43  add     rax, 2
0x18000dd47  dec     r9
0x18000dd4a  sub     rdx, 1
0x18000dd4e  jnz     short loc_18000DD2C
0x18000dd50  test    rdx, rdx
0x18000dd53  lea     rcx, [rax-2]
0x18000dd57  mov     rdx, rbx
0x18000dd5a  cmovnz  rcx, rax
0x18000dd5e  lea     rax, [rsp+270h+Name]
0x18000dd63  mov     [rcx], r12w
0x18000dd67  cmp     [rax], r12w
0x18000dd6b  jz      short loc_18000DD77
0x18000dd6d  add     rax, 2
0x18000dd71  sub     rdx, 1
0x18000dd75  jnz     short loc_18000DD67
0x18000dd77  mov     rcx, rbx
0x18000dd7a  mov     rax, rdx
0x18000dd7d  sub     rcx, rdx
0x18000dd80  neg     rax
0x18000dd83  sbb     r8, r8
0x18000dd86  and     r8, rcx
0x18000dd89  test    rdx, rdx
0x18000dd8c  jnz     loc_18000DED4
0x18000dd92  lea     r8, [rsp+270h+Name]; lpName
0x18000dd97  xor     edx, edx; bInheritHandle
0x18000dd99  mov     ecx, 1F0003h; dwDesiredAccess
0x18000dd9e  call    cs:__imp_OpenSemaphoreW
0x18000dda4  mov     rdi, rax
0x18000dda7  test    rax, rax
0x18000ddaa  jz      loc_18000DE6D
0x18000ddb0  lea     rdx, [rsp+270h+var_24C]; int *
0x18000ddb5  mov     [rsp+270h+var_24C], r12d
0x18000ddba  mov     rcx, rax; hHandle
0x18000ddbd  mov     [rsp+270h+var_250], r12d; int
0x18000ddc2  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18000ddc7  mov     esi, eax
0x18000ddc9  test    eax, eax
0x18000ddcb  js      loc_18000DF71
0x18000ddd1  mov     rdx, rbx
0x18000ddd4  lea     rax, [rsp+270h+Name]
0x18000ddd9  cmp     [rax], r12w
0x18000dddd  jz      short loc_18000DDE9
0x18000dddf  add     rax, 2
0x18000dde3  sub     rdx, 1
0x18000dde7  jnz     short loc_18000DDD9
0x18000dde9  mov     rcx, rbx
0x18000ddec  mov     rax, rdx
0x18000ddef  sub     rcx, rdx
0x18000ddf2  neg     rax
0x18000ddf5  sbb     r8, r8
0x18000ddf8  and     r8, rcx
0x18000ddfb  test    rdx, rdx
0x18000ddfe  jnz     loc_18000DF27
0x18000de04  lea     r8, [rsp+270h+Name]; lpName
0x18000de09  xor     edx, edx; bInheritHandle
0x18000de0b  mov     ecx, 1F0003h; dwDesiredAccess
0x18000de10  call    cs:__imp_OpenSemaphoreW
0x18000de16  mov     rbx, rax
0x18000de19  test    rax, rax
0x18000de1c  jnz     short loc_18000DE92
0x18000de1e  mov     rcx, [rbp+178h]; this
0x18000de25  lea     r8, aWil; "wil"
0x18000de2c  mov     edx, 0DCh; void *
0x18000de31  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000de36  mov     esi, eax
0x18000de38  mov     rcx, rdi; this
0x18000de3b  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x18000de40  mov     eax, esi
0x18000de42  mov     rcx, [rbp+170h+var_30]
0x18000de49  xor     rcx, rsp; StackCookie
0x18000de4c  call    __security_check_cookie
0x18000de51  lea     r11, [rsp+270h+var_20]
0x18000de59  mov     rbx, [r11+30h]
0x18000de5d  mov     rsi, [r11+38h]
0x18000de61  mov     rsp, r11
0x18000de64  pop     r15
0x18000de66  pop     r14
0x18000de68  pop     r12
0x18000de6a  pop     rdi
0x18000de6b  pop     rbp
0x18000de6c  retn
0x18000de6d  call    cs:__imp_GetLastError
0x18000de73  cmp     eax, 2
0x18000de76  jz      short loc_18000DECD
0x18000de78  mov     rcx, [rbp+178h]; this
0x18000de7f  lea     r8, aWil; "wil"
0x18000de86  mov     edx, 0D0h; void *
0x18000de8b  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000de90  jmp     short loc_18000DE42
0x18000de92  lea     rdx, [rsp+270h+var_250]; int *
0x18000de97  mov     rcx, rbx; hHandle
0x18000de9a  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18000de9f  mov     esi, eax
0x18000dea1  test    eax, eax
0x18000dea3  js      loc_18000DF91
0x18000dea9  mov     rcx, rbx; this
0x18000deac  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x18000deb1  movsxd  rax, [rsp+270h+var_24C]
0x18000deb6  movsxd  rcx, [rsp+270h+var_250]
0x18000debb  shl     rcx, 1Fh
0x18000debf  or      rcx, rax
0x18000dec2  mov     [r15], rcx
0x18000dec5  mov     rcx, rdi; this
0x18000dec8  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x18000decd  xor     eax, eax
0x18000decf  jmp     loc_18000DE42
0x18000ded4  mov     rax, rbx
0x18000ded7  lea     rdx, [rsp+270h+Name]
0x18000dedc  lea     r9, aP0; "_p0"
0x18000dee3  mov     rcx, r14
0x18000dee6  lea     rdx, [rdx+r8*2]
0x18000deea  sub     rax, r8
0x18000deed  jz      short loc_18000DF13
0x18000deef  test    rcx, rcx
0x18000def2  jz      short loc_18000DF13
0x18000def4  movzx   r8d, word ptr [r9]
0x18000def8  test    r8w, r8w
0x18000defc  jz      short loc_18000DF13
0x18000defe  mov     [rdx], r8w
0x18000df02  add     r9, 2
0x18000df06  add     rdx, 2
0x18000df0a  dec     rcx
0x18000df0d  sub     rax, 1
0x18000df11  jnz     short loc_18000DEEF
0x18000df13  test    rax, rax
0x18000df16  lea     rcx, [rdx-2]
0x18000df1a  cmovnz  rcx, rdx
0x18000df1e  mov     [rcx], r12w
0x18000df22  jmp     loc_18000DD92
0x18000df27  lea     rax, [rsp+270h+Name]
0x18000df2c  lea     rax, [rax+r8*2]
0x18000df30  lea     rcx, asc_180043ED8; "h"
0x18000df37  sub     rbx, r8
0x18000df3a  jz      short loc_18000DF5D
0x18000df3c  test    r14, r14
0x18000df3f  jz      short loc_18000DF5D
0x18000df41  movzx   edx, word ptr [rcx]
0x18000df44  test    dx, dx
0x18000df47  jz      short loc_18000DF5D
0x18000df49  mov     [rax], dx
0x18000df4c  add     rcx, 2
0x18000df50  add     rax, 2
0x18000df54  dec     r14
0x18000df57  sub     rbx, 1
0x18000df5b  jnz     short loc_18000DF3C
0x18000df5d  test    rbx, rbx
0x18000df60  lea     rdx, [rax-2]
0x18000df64  cmovnz  rdx, rax
0x18000df68  mov     [rdx], r12w
0x18000df6c  jmp     loc_18000DE04
0x18000df71  mov     rcx, [rbp+178h]; this
0x18000df78  lea     r8, aWil; "wil"
0x18000df7f  mov     r9d, eax; char *
0x18000df82  mov     edx, 0D6h; void *
0x18000df87  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000df8c  jmp     loc_18000DE38
0x18000df91  mov     rcx, [rbp+178h]; this
0x18000df98  lea     r8, aWil; "wil"
0x18000df9f  mov     r9d, eax; char *
0x18000dfa2  mov     edx, 0DEh; void *
0x18000dfa7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000dfac  mov     rcx, rbx; this
0x18000dfaf  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x18000dfb4  jmp     loc_18000DE38
```
