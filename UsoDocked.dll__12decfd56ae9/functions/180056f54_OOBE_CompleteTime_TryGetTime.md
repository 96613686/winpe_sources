# OOBE::CompleteTime::TryGetTime

- ea: `0x180056f54`
- end: `0x18005719c`
- name: `OOBE::CompleteTime::TryGetTime`
- size: `584`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180055430`

## callees

- `0x1800183f4`
- `0x180056c84`
- `0x180056f54`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180057078`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180057078`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180057128`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180057173`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180057128`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180057173`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180057189`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180057189`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180056fbd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18005702d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180056fbd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18005702d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180056ffc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180057098`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800570e7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800570f8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180056ffc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180057098`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800570e7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800570f8`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x180056fad`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x180056fe9`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x180056fad`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x180056fe9`

## string_xrefs

- `0x1800570cc`: `onecoreuap\internal\shell\inc\OOBECompleteTime.h`
- `0x180056fa6`: `OOBECompleteTimestamp`
- `0x180056fe2`: `OOBECompleteTimestamp`
- `0x18005711b`: `OOBECompleteTimestamp`
- `0x180056f9f`: `Software\Microsoft\Windows\CurrentVersion\OOBE\OOBECompleteTimestamp`
- `0x180056fdb`: `Software\Microsoft\Windows\CurrentVersion\OOBE\OOBECompleteTimestamp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall OOBE::CompleteTime::TryGetTime(bool *a1, _OWORD *a2)
{
  LPVOID v4; // rax
  void *v5; // rbx
  WCHAR *v6; // rax
  const unsigned __int16 *v7; // r8
  unsigned int v8; // ebx
  LSTATUS v9; // eax
  signed int v10; // ebx
  unsigned __int16 **phkResult; // [rsp+20h] [rbp-30h]
  int phkResulta; // [rsp+20h] [rbp-30h]
  unsigned __int64 *pvData; // [rsp+28h] [rbp-28h]
  unsigned int pcbData; // [rsp+30h] [rbp-20h]
  HKEY hkey[2]; // [rsp+40h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+28h]
  SIZE_T cb; // [rsp+80h] [rbp+30h] BYREF
  DWORD v19; // [rsp+90h] [rbp+40h] BYREF
  LPCWSTR lpSubKey; // [rsp+98h] [rbp+48h] BYREF

  *a1 = 0;
  v19 = 16;
  *a2 = 0;
  hkey[0] = 0;
  lpSubKey = 0;
  LODWORD(cb) = 0;
  phkResult = (unsigned __int16 **)&cb;
  if ( (unsigned int)GetPersistedRegistryLocationW(
                       L"OOBECompleteTimestamp",
                       L"Software\\Microsoft\\Windows\\CurrentVersion\\OOBE\\OOBECompleteTimestamp",
                       &lpSubKey,
                       0) == 234 )
  {
    v4 = CoTaskMemAlloc((unsigned int)cb);
    v5 = v4;
    if ( v4 )
    {
      phkResult = 0;
      if ( (unsigned int)GetPersistedRegistryLocationW(
                           L"OOBECompleteTimestamp",
                           L"Software\\Microsoft\\Windows\\CurrentVersion\\OOBE\\OOBECompleteTimestamp",
                           v4,
                           (unsigned int)cb) )
        CoTaskMemFree(v5);
      else
        lpSubKey = (LPCWSTR)v5;
    }
  }
  if ( lpSubKey )
    goto LABEL_10;
  lpSubKey = 0;
  hkey[1] = 0;
  if ( !is_mul_ok(0x45u, 2u) )
  {
    v8 = -2147024362;
LABEL_18:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2E,
      (unsigned int)"onecoreuap\\internal\\shell\\inc\\OobeRedirectionKeyHelper.h",
      (const char *)v8,
      (int)phkResult);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x16,
      (unsigned int)"onecoreuap\\internal\\shell\\inc\\OOBECompleteTime.h",
      (const char *)v8,
      phkResulta);
    if ( lpSubKey )
      CoTaskMemFree((LPVOID)lpSubKey);
    goto LABEL_23;
  }
  v6 = (WCHAR *)CoTaskMemAlloc(0x8Au);
  lpSubKey = v6;
  v8 = v6 == 0 ? 0x8007000E : 0;
  if ( !v6 )
    goto LABEL_18;
  StringCchCopyNExW(v6, 0x45u, v7, 0x44u, phkResult, pvData, pcbData);
LABEL_10:
  v9 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, lpSubKey, 0, 0x2001Fu, hkey);
  v10 = v9;
  if ( !v9 )
  {
    if ( lpSubKey )
      CoTaskMemFree((LPVOID)lpSubKey);
    goto LABEL_22;
  }
  if ( v9 > 0 )
    v10 = (unsigned __int16)v9 | 0x80070000;
  if ( lpSubKey )
    CoTaskMemFree((LPVOID)lpSubKey);
  if ( v10 >= 0 )
LABEL_22:
    *a1 = RegGetValueW(hkey[0], 0, L"OOBECompleteTimestamp", 0x20000008u, 0, a2, &v19) == 0;
LABEL_23:
  if ( !*a1 )
  {
    v19 = 16;
    *a1 = RegGetValueW(
            HKEY_LOCAL_MACHINE,
            L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\OOBE\\Stats",
            L"EndTimeStamp",
            0x20000008u,
            0,
            a2,
            &v19) == 0;
  }
  if ( hkey[0] )
    RegCloseKey(hkey[0]);
  return 0;
}

```

## disassembly

```asm
0x180056f54  push    rbp
0x180056f56  push    rbx
0x180056f57  push    rsi
0x180056f58  push    rdi
0x180056f59  push    r15
0x180056f5b  mov     rbp, rsp
0x180056f5e  sub     rsp, 50h
0x180056f62  mov     rsi, rdx
0x180056f65  mov     rdi, rcx
0x180056f68  mov     byte ptr [rcx], 0
0x180056f6b  mov     [rbp+arg_10], 10h
0x180056f72  xorps   xmm0, xmm0
0x180056f75  movups  xmmword ptr [rdx], xmm0
0x180056f78  mov     [rbp+hkey], 0
0x180056f80  mov     [rbp+lpSubKey], 0
0x180056f88  mov     dword ptr [rbp+cb], 0
0x180056f8f  lea     rax, [rbp+cb]
0x180056f93  mov     [rsp+50h+phkResult], rax
0x180056f98  xor     r9d, r9d
0x180056f9b  lea     r8, [rbp+lpSubKey]
0x180056f9f  lea     rdx, aSoftwareMicros_8; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180056fa6  lea     rcx, aOobecompleteti; "OOBECompleteTimestamp"
0x180056fad  call    cs:__imp_GetPersistedRegistryLocationW
0x180056fb3  cmp     eax, 0EAh
0x180056fb8  jnz     short loc_180057002
0x180056fba  mov     ecx, dword ptr [rbp+cb]; cb
0x180056fbd  call    cs:__imp_CoTaskMemAlloc
0x180056fc3  mov     rbx, rax
0x180056fc6  test    rax, rax
0x180056fc9  jz      short loc_180057002
0x180056fcb  mov     [rsp+50h+phkResult], 0; int
0x180056fd4  mov     r9d, dword ptr [rbp+cb]
0x180056fd8  mov     r8, rax
0x180056fdb  lea     rdx, aSoftwareMicros_8; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180056fe2  lea     rcx, aOobecompleteti; "OOBECompleteTimestamp"
0x180056fe9  call    cs:__imp_GetPersistedRegistryLocationW
0x180056fef  test    eax, eax
0x180056ff1  jnz     short loc_180056FF9
0x180056ff3  mov     [rbp+lpSubKey], rbx
0x180056ff7  jmp     short loc_180057002
0x180056ff9  mov     rcx, rbx; pv
0x180056ffc  call    cs:__imp_CoTaskMemFree
0x180057002  cmp     [rbp+lpSubKey], 0
0x180057007  jnz     short loc_18005705B
0x180057009  mov     [rbp+lpSubKey], 0
0x180057011  mov     [rbp+var_8], 0
0x180057019  mov     eax, 2
0x18005701e  lea     r15d, [rax+43h]
0x180057022  mul     r15
0x180057025  test    rdx, rdx
0x180057028  jnz     short loc_1800570A8
0x18005702a  mov     rcx, rax; cb
0x18005702d  call    cs:__imp_CoTaskMemAlloc
0x180057033  mov     [rbp+lpSubKey], rax
0x180057037  mov     rcx, rax
0x18005703a  neg     rcx
0x18005703d  sbb     ebx, ebx
0x18005703f  not     ebx
0x180057041  and     ebx, 8007000Eh
0x180057047  test    rax, rax
0x18005704a  jz      short loc_1800570AD
0x18005704c  lea     r9d, [r15-1]; unsigned __int64
0x180057050  mov     edx, r15d; unsigned __int64
0x180057053  mov     rcx, rax; unsigned __int16 *
0x180057056  call    ?StringCchCopyNExW@@YAJPEAG_KPEBG1PEAPEAGPEA_KK@Z; StringCchCopyNExW(ushort *,unsigned __int64,ushort const *,unsigned __int64,ushort * *,unsigned __int64 *,ulong)
0x18005705b  lea     rax, [rbp+hkey]
0x18005705f  mov     [rsp+50h+phkResult], rax; phkResult
0x180057064  mov     r9d, 2001Fh; samDesired
0x18005706a  xor     r8d, r8d; ulOptions
0x18005706d  mov     rdx, [rbp+lpSubKey]; lpSubKey
0x180057071  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180057078  call    cs:__imp_RegOpenKeyExW
0x18005707e  mov     ebx, eax
0x180057080  test    eax, eax
0x180057082  jz      short loc_1800570EF
0x180057084  jle     short loc_18005708F
0x180057086  movzx   ebx, ax
0x180057089  or      ebx, 80070000h
0x18005708f  mov     rcx, [rbp+lpSubKey]; pv
0x180057093  test    rcx, rcx
0x180057096  jz      short loc_18005709E
0x180057098  call    cs:__imp_CoTaskMemFree
0x18005709e  test    ebx, ebx
0x1800570a0  js      loc_180057135
0x1800570a6  jmp     short loc_1800570FE
0x1800570a8  mov     ebx, 80070216h
0x1800570ad  mov     rcx, [rbp+28h]; this
0x1800570b1  mov     r9d, ebx; char *
0x1800570b4  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\shell\\inc\\OobeR"...
0x1800570bb  mov     edx, 2Eh ; '.'; void *
0x1800570c0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800570c5  mov     rcx, [rbp+28h]; this
0x1800570c9  mov     r9d, ebx; char *
0x1800570cc  lea     r8, aOnecoreuapInte_1; "onecoreuap\\internal\\shell\\inc\\OOBEC"...
0x1800570d3  mov     edx, 16h; void *
0x1800570d8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800570dd  nop
0x1800570de  mov     rcx, [rbp+lpSubKey]; pv
0x1800570e2  test    rcx, rcx
0x1800570e5  jz      short loc_180057135
0x1800570e7  call    cs:__imp_CoTaskMemFree
0x1800570ed  jmp     short loc_180057135
0x1800570ef  mov     rcx, [rbp+lpSubKey]; pv
0x1800570f3  test    rcx, rcx
0x1800570f6  jz      short loc_1800570FE
0x1800570f8  call    cs:__imp_CoTaskMemFree
0x1800570fe  lea     rax, [rbp+arg_10]
0x180057102  mov     qword ptr [rsp+50h+pcbData], rax; pcbData
0x180057107  mov     [rsp+50h+pvData], rsi; pvData
0x18005710c  mov     [rsp+50h+phkResult], 0; pdwType
0x180057115  mov     r9d, 20000008h; dwFlags
0x18005711b  lea     r8, aOobecompleteti; "OOBECompleteTimestamp"
0x180057122  xor     edx, edx; lpSubKey
0x180057124  mov     rcx, [rbp+hkey]; hkey
0x180057128  call    cs:__imp_RegGetValueW
0x18005712e  test    eax, eax
0x180057130  setz    al
0x180057133  mov     [rdi], al
0x180057135  cmp     byte ptr [rdi], 0
0x180057138  jnz     short loc_180057180
0x18005713a  mov     [rbp+arg_10], 10h
0x180057141  lea     rax, [rbp+arg_10]
0x180057145  mov     qword ptr [rsp+50h+pcbData], rax; pcbData
0x18005714a  mov     [rsp+50h+pvData], rsi; pvData
0x18005714f  mov     [rsp+50h+phkResult], 0; pdwType
0x180057158  mov     r9d, 20000008h; dwFlags
0x18005715e  lea     r8, aEndtimestamp; "EndTimeStamp"
0x180057165  lea     rdx, aSoftwareMicros_14; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x18005716c  mov     rcx, 0FFFFFFFF80000002h; hkey
0x180057173  call    cs:__imp_RegGetValueW
0x180057179  test    eax, eax
0x18005717b  setz    al
0x18005717e  mov     [rdi], al
0x180057180  mov     rcx, [rbp+hkey]; hKey
0x180057184  test    rcx, rcx
0x180057187  jz      short loc_18005718F
0x180057189  call    cs:__imp_RegCloseKey
0x18005718f  xor     eax, eax
0x180057191  add     rsp, 50h
0x180057195  pop     r15
0x180057197  pop     rdi
0x180057198  pop     rsi
0x180057199  pop     rbx
0x18005719a  pop     rbp
0x18005719b  retn
```
