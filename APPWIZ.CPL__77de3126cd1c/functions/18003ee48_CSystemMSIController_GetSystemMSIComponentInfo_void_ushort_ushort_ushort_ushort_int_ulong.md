# CSystemMSIController::_GetSystemMSIComponentInfo(void *,ushort *,ushort * *,ushort * *,ushort * *,int *,ulong *)

- ea: `0x18003ee48`
- end: `0x18003ef5e`
- name: `?_GetSystemMSIComponentInfo@CSystemMSIController@@AEAAKPEAXPEAGPEAPEAG22PEAHPEAK@Z`
- size: `278`
- prototype: `unsigned int __fastcall(CSystemMSIController *__hidden this, void *, unsigned __int16 *, unsigned __int16 **, unsigned __int16 **, unsigned __int16 **, int *, unsigned int *)`
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x18003ea60`

## callees

- `0x18003ee48`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003eeb5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003eeb5`
- `osbaseln!GetOsBaselineComponentInfoW` at `0x18003ee91`
- `osbaseln!GetOsBaselineComponentInfoW` at `0x18003eee8`
- `osbaseln!GetOsBaselineComponentInfoW` at `0x18003ee91`
- `osbaseln!GetOsBaselineComponentInfoW` at `0x18003eee8`
- `osbaseln!GetOsInstalledComponentInfoW` at `0x18003ef18`
- `osbaseln!GetOsInstalledComponentInfoW` at `0x18003ef18`

## pseudocode

```c
__int64 __fastcall CSystemMSIController::_GetSystemMSIComponentInfo(
        CSystemMSIController *this,
        void *a2,
        unsigned __int16 *a3,
        unsigned __int16 **a4,
        unsigned __int16 **a5,
        unsigned __int16 **a6,
        int *a7,
        unsigned int *a8)
{
  unsigned int *v8; // rsi
  unsigned int OsBaselineComponentInfoW; // eax
  unsigned int v13; // ecx
  SIZE_T v14; // rcx
  unsigned __int16 *v15; // rax
  unsigned int OsInstalledComponentInfoW; // eax
  unsigned int v18; // [rsp+70h] [rbp+8h] BYREF
  int v19; // [rsp+74h] [rbp+Ch]

  v19 = HIDWORD(this);
  v8 = a8;
  v18 = 0;
  OsBaselineComponentInfoW = GetOsBaselineComponentInfoW(a2, a3, 0, &v18, 0, 0, a8);
  v13 = OsBaselineComponentInfoW;
  if ( OsBaselineComponentInfoW == 122 || !OsBaselineComponentInfoW )
  {
    v14 = 2 * v18;
    if ( (unsigned int)v14 <= v18 )
    {
      return 8;
    }
    else
    {
      v15 = (unsigned __int16 *)CoTaskMemAlloc(v14);
      *a4 = v15;
      if ( v15 )
        v13 = GetOsBaselineComponentInfoW(a2, a3, v15, &v18, 0, 0, v8);
      else
        v13 = 8;
      if ( !v13 )
      {
        OsInstalledComponentInfoW = GetOsInstalledComponentInfoW(a3, 0, 0, 0, 0, 0);
        v13 = OsInstalledComponentInfoW;
        if ( OsInstalledComponentInfoW == 1168 )
        {
          v13 = 0;
          *a7 = 0;
        }
        else if ( !OsInstalledComponentInfoW )
        {
          *a7 = 1;
        }
      }
    }
  }
  return v13;
}

```

## disassembly

```asm
0x18003ee48  mov     rax, rsp
0x18003ee4b  mov     [rax+8], rcx
0x18003ee4f  push    rbx
0x18003ee50  push    rsi
0x18003ee51  push    rdi
0x18003ee52  push    r14
0x18003ee54  sub     rsp, 48h
0x18003ee58  mov     rsi, [rsp+68h+arg_38]
0x18003ee60  mov     rbx, r8
0x18003ee63  mov     rdi, rdx
0x18003ee66  mov     [rax-38h], rsi
0x18003ee6a  mov     r14, r9
0x18003ee6d  mov     qword ptr [rax-40h], 0
0x18003ee75  lea     r9, [rax+8]
0x18003ee79  mov     qword ptr [rax-48h], 0
0x18003ee81  xor     r8d, r8d
0x18003ee84  mov     dword ptr [rax+8], 0
0x18003ee8b  mov     rdx, rbx
0x18003ee8e  mov     rcx, rdi
0x18003ee91  call    cs:__imp_GetOsBaselineComponentInfoW
0x18003ee97  mov     ecx, eax
0x18003ee99  cmp     eax, 7Ah ; 'z'
0x18003ee9c  jz      short loc_18003EEA6
0x18003ee9e  test    eax, eax
0x18003eea0  jnz     loc_18003EF52
0x18003eea6  mov     eax, [rsp+68h+arg_0]
0x18003eeaa  lea     ecx, [rax+rax]; cb
0x18003eead  cmp     ecx, eax
0x18003eeaf  jbe     loc_18003EF4D
0x18003eeb5  call    cs:__imp_CoTaskMemAlloc
0x18003eebb  mov     [r14], rax
0x18003eebe  test    rax, rax
0x18003eec1  jz      short loc_18003EEF2
0x18003eec3  mov     [rsp+68h+var_38], rsi
0x18003eec8  lea     r9, [rsp+68h+arg_0]
0x18003eecd  mov     [rsp+68h+var_40], 0
0x18003eed6  mov     r8, rax
0x18003eed9  mov     rdx, rbx
0x18003eedc  mov     [rsp+68h+var_48], 0
0x18003eee5  mov     rcx, rdi
0x18003eee8  call    cs:__imp_GetOsBaselineComponentInfoW
0x18003eeee  mov     ecx, eax
0x18003eef0  jmp     short loc_18003EEF7
0x18003eef2  mov     ecx, 8
0x18003eef7  test    ecx, ecx
0x18003eef9  jnz     short loc_18003EF52
0x18003eefb  mov     [rsp+68h+var_40], 0
0x18003ef04  xor     r9d, r9d
0x18003ef07  xor     r8d, r8d
0x18003ef0a  mov     [rsp+68h+var_48], 0
0x18003ef13  xor     edx, edx
0x18003ef15  mov     rcx, rbx
0x18003ef18  call    cs:__imp_GetOsInstalledComponentInfoW
0x18003ef1e  mov     ecx, eax
0x18003ef20  cmp     eax, 490h
0x18003ef25  jnz     short loc_18003EF39
0x18003ef27  mov     rax, [rsp+68h+arg_30]
0x18003ef2f  xor     ecx, ecx
0x18003ef31  mov     dword ptr [rax], 0
0x18003ef37  jmp     short loc_18003EF52
0x18003ef39  test    eax, eax
0x18003ef3b  jnz     short loc_18003EF52
0x18003ef3d  mov     rax, [rsp+68h+arg_30]
0x18003ef45  mov     dword ptr [rax], 1
0x18003ef4b  jmp     short loc_18003EF52
0x18003ef4d  mov     ecx, 8
0x18003ef52  mov     eax, ecx
0x18003ef54  add     rsp, 48h
0x18003ef58  pop     r14
0x18003ef5a  pop     rdi
0x18003ef5b  pop     rsi
0x18003ef5c  pop     rbx
0x18003ef5d  retn
```
