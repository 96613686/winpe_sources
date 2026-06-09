# CSLSRequest::AppendFromTestKeyOverrideWithDefault(wchar_t *,unsigned __int64,wchar_t const *,wchar_t const *,wchar_t * *,unsigned __int64 *,bool *)

- ea: `0x140032fd0`
- end: `0x140033159`
- name: `?AppendFromTestKeyOverrideWithDefault@CSLSRequest@@AEBAJPEA_W_KPEB_W2PEAPEA_WPEA_KPEA_N@Z`
- size: `393`
- prototype: `__int64 __fastcall(CSLSRequest *this, wchar_t *, unsigned __int64, const wchar_t *, WCHAR *lpString1, wchar_t **, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callers

- `0x140032cc0`

## callees

- `0x140003de4`
- `0x140017bd0`
- `0x140032fd0`
- `0x140033160`
- `0x140045dc0`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x140033091`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x140033091`

## string_xrefs

- `0x140033059`: `Software\Microsoft\Windows\CurrentVersion\WindowsUpdate\Test`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CSLSRequest::AppendFromTestKeyOverrideWithDefault(
        CSLSRequest *this,
        wchar_t *a2,
        unsigned __int64 a3,
        const wchar_t *a4,
        WCHAR *lpString1,
        wchar_t **a6,
        unsigned __int64 *a7,
        bool *a8)
{
  unsigned __int64 v9; // r14
  wchar_t *v10; // rbp
  WCHAR *v11; // rsi
  __int64 v12; // r10
  WCHAR *v13; // rax
  unsigned int v14; // r9d
  unsigned int v15; // eax
  unsigned int v17; // [rsp+30h] [rbp-288h]
  wchar_t *v18; // [rsp+48h] [rbp-270h] BYREF
  unsigned __int64 v19; // [rsp+50h] [rbp-268h] BYREF
  WCHAR String2[264]; // [rsp+60h] [rbp-258h] BYREF

  v9 = a3;
  v10 = a2;
  v11 = lpString1;
  v18 = a2;
  v19 = a3;
  if ( a8 )
    *a8 = 0;
  if ( (unsigned int)AreTestKeysAllowed()
    && (int)RegQueryStringValue(
              0,
              L"Software\\Microsoft\\Windows\\CurrentVersion\\WindowsUpdate\\Test",
              (__int64)a4,
              (__int64)String2,
              260) >= 0 )
  {
    v11 = String2;
    if ( a8 && CompareStringW(0x7Fu, 1u, lpString1, -1, String2, -1) != 2 )
      *a8 = 1;
  }
  else if ( !lpString1 )
  {
    v14 = -2147024809;
    goto LABEL_15;
  }
  v12 = 260;
  v13 = v11;
  do
  {
    if ( !*v13 )
      break;
    ++v13;
    --v12;
  }
  while ( v12 );
  v14 = v12 == 0 ? 0x80070057 : 0;
  if ( v12 )
  {
    v15 = StringCchCatNExW(v10, v9, v11, ((260 - v12) & -(__int64)(v12 != 0)) + 1, &v18, &v19, v17);
    v10 = v18;
    v14 = v15;
    v9 = v19;
  }
LABEL_15:
  *a6 = v10;
  *a7 = v9;
  return v14;
}

```

## disassembly

```asm
0x140032fd0  mov     [rsp+arg_0], rbx
0x140032fd5  push    rbp
0x140032fd6  push    rsi
0x140032fd7  push    rdi
0x140032fd8  push    r12
0x140032fda  push    r13
0x140032fdc  push    r14
0x140032fde  push    r15
0x140032fe0  sub     rsp, 280h
0x140032fe7  mov     rax, cs:__security_cookie
0x140032fee  xor     rax, rsp
0x140032ff1  mov     [rsp+2B8h+var_48], rax
0x140032ff9  mov     rax, [rsp+2B8h+arg_30]
0x140033001  mov     r12, r9
0x140033004  mov     rbx, [rsp+2B8h+arg_38]
0x14003300c  mov     r14, r8
0x14003300f  mov     r15, [rsp+2B8h+lpString1]
0x140033017  mov     rbp, rdx
0x14003301a  mov     r13, [rsp+2B8h+arg_28]
0x140033022  mov     rsi, r15
0x140033025  mov     [rsp+2B8h+var_278], rax
0x14003302a  xor     eax, eax
0x14003302c  mov     [rsp+2B8h+var_270], rdx
0x140033031  mov     [rsp+2B8h+var_268], r8
0x140033036  test    rbx, rbx
0x140033039  jz      short loc_14003303D
0x14003303b  mov     [rbx], al
0x14003303d  call    ?AreTestKeysAllowed@@YAH_N@Z; AreTestKeysAllowed(bool)
0x140033042  xor     ecx, ecx
0x140033044  mov     edi, 104h
0x140033049  test    eax, eax
0x14003304b  jz      short loc_1400330A3
0x14003304d  lea     r9, [rsp+2B8h+String2]
0x140033052  mov     dword ptr [rsp+2B8h+lpString2], edi
0x140033056  mov     r8, r12
0x140033059  lea     rdx, ?c_szRegWUTest@@3QB_WB; "Software\\Microsoft\\Windows\\CurrentVe"...
0x140033060  call    ?RegQueryStringValue@@YAJPEAUHKEY__@@PEB_W1PEA_WKW4RegistryHiveType@@@Z; RegQueryStringValue(HKEY__ *,wchar_t const *,wchar_t const *,wchar_t *,ulong,RegistryHiveType)
0x140033065  xor     ecx, ecx
0x140033067  test    eax, eax
0x140033069  js      short loc_1400330A3
0x14003306b  lea     rsi, [rsp+2B8h+String2]
0x140033070  test    rbx, rbx
0x140033073  jz      short loc_1400330A8
0x140033075  or      r9d, 0FFFFFFFFh; cchCount1
0x140033079  lea     edx, [rcx+1]; dwCmpFlags
0x14003307c  lea     rax, [rsp+2B8h+String2]
0x140033081  mov     [rsp+2B8h+cchCount2], r9d; cchCount2
0x140033086  lea     ecx, [rdx+7Eh]; Locale
0x140033089  mov     [rsp+2B8h+lpString2], rax; lpString2
0x14003308e  mov     r8, r15; lpString1
0x140033091  call    cs:__imp_CompareStringW
0x140033097  xor     ecx, ecx
0x140033099  cmp     eax, 2
0x14003309c  jz      short loc_1400330A8
0x14003309e  mov     byte ptr [rbx], 1
0x1400330a1  jmp     short loc_1400330A8
0x1400330a3  test    r15, r15
0x1400330a6  jz      short loc_140033119
0x1400330a8  mov     r10, rdi
0x1400330ab  mov     rax, rsi
0x1400330ae  cmp     [rax], cx
0x1400330b1  jz      short loc_1400330BD
0x1400330b3  add     rax, 2
0x1400330b7  sub     r10, 1
0x1400330bb  jnz     short loc_1400330AE
0x1400330bd  mov     rax, r10
0x1400330c0  neg     rax
0x1400330c3  mov     rax, r10
0x1400330c6  sbb     r9d, r9d
0x1400330c9  sub     rdi, r10
0x1400330cc  not     r9d
0x1400330cf  and     r9d, 80070057h
0x1400330d6  neg     rax
0x1400330d9  sbb     r8, r8
0x1400330dc  and     r8, rdi
0x1400330df  test    r10, r10
0x1400330e2  jz      short loc_14003311F
0x1400330e4  lea     rax, [rsp+2B8h+var_268]
0x1400330e9  mov     rdx, r14; unsigned __int64
0x1400330ec  mov     qword ptr [rsp+2B8h+cchCount2], rax; unsigned __int64 *
0x1400330f1  lea     r9, [r8+1]; unsigned __int64
0x1400330f5  lea     rax, [rsp+2B8h+var_270]
0x1400330fa  mov     r8, rsi; wchar_t *
0x1400330fd  mov     rcx, rbp; wchar_t *
0x140033100  mov     [rsp+2B8h+lpString2], rax; wchar_t **
0x140033105  call    ?StringCchCatNExW@@YAJPEA_W_KPEB_W1PEAPEA_WPEA_KK@Z; StringCchCatNExW(wchar_t *,unsigned __int64,wchar_t const *,unsigned __int64,wchar_t * *,unsigned __int64 *,ulong)
0x14003310a  mov     rbp, [rsp+2B8h+var_270]
0x14003310f  mov     r9d, eax
0x140033112  mov     r14, [rsp+2B8h+var_268]
0x140033117  jmp     short loc_14003311F
0x140033119  mov     r9d, 80070057h
0x14003311f  mov     rax, [rsp+2B8h+var_278]
0x140033124  mov     [r13+0], rbp
0x140033128  mov     [rax], r14
0x14003312b  mov     eax, r9d
0x14003312e  mov     rcx, [rsp+2B8h+var_48]
0x140033136  xor     rcx, rsp; StackCookie
0x140033139  call    __security_check_cookie
0x14003313e  mov     rbx, [rsp+2B8h+arg_0]
0x140033146  add     rsp, 280h
0x14003314d  pop     r15
0x14003314f  pop     r14
0x140033151  pop     r13
0x140033153  pop     r12
0x140033155  pop     rdi
0x140033156  pop     rsi
0x140033157  pop     rbp
0x140033158  retn
```
