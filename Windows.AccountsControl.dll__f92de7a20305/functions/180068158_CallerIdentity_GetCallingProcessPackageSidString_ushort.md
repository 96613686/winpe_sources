# CallerIdentity::GetCallingProcessPackageSidString(ushort * *)

- ea: `0x180068158`
- end: `0x1800681eb`
- name: `?GetCallingProcessPackageSidString@CallerIdentity@@YAJPEAPEAG@Z`
- size: `147`
- prototype: `__int64 __fastcall(LPWSTR *StringSid, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180024888`

## callees

- `0x180015fd4`
- `0x180024118`
- `0x180067df0`
- `0x180068158`
- `0x180068384`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800681cc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800681cc`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800681b2`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800681b2`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CallerIdentity::GetCallingProcessPackageSidString(
        LPWSTR *StringSid,
        unsigned __int16 **a2,
        void **a3)
{
  int CallingProcessHandle; // ebx
  void **v5; // r8
  PSID Sid; // [rsp+30h] [rbp+8h] BYREF
  CallerIdentity *v8; // [rsp+38h] [rbp+10h] BYREF

  *StringSid = 0;
  v8 = 0;
  CallingProcessHandle = CallerIdentity::GetCallingProcessHandle((CallerIdentity *)StringSid, (unsigned int)&v8, a3);
  if ( CallingProcessHandle >= 0 )
  {
    *StringSid = 0;
    Sid = 0;
    CallingProcessHandle = CallerIdentity::GetPackageSidFromProcessHandle(v8, &Sid, v5);
    if ( CallingProcessHandle >= 0 )
    {
      if ( ConvertSidToStringSidW(Sid, StringSid) )
        CallingProcessHandle = 0;
      else
        CallingProcessHandle = ResultFromKnownLastError();
      LocalFree(Sid);
    }
  }
  CTSmartObj<void *,CAutoHandle_Policy<void *>>::~CTSmartObj<void *,CAutoHandle_Policy<void *>>(&v8);
  return (unsigned int)CallingProcessHandle;
}

```

## disassembly

```asm
0x180068158  mov     [rsp+arg_10], rbx
0x18006815d  push    rdi
0x18006815e  sub     rsp, 20h
0x180068162  mov     rdi, rcx
0x180068165  mov     qword ptr [rcx], 0
0x18006816c  mov     [rsp+28h+arg_8], 0
0x180068175  lea     rdx, [rsp+28h+arg_8]; unsigned int
0x18006817a  call    ?GetCallingProcessHandle@CallerIdentity@@YAJKPEAPEAX@Z; CallerIdentity::GetCallingProcessHandle(ulong,void * *)
0x18006817f  mov     ebx, eax
0x180068181  test    eax, eax
0x180068183  js      short loc_1800681D3
0x180068185  mov     qword ptr [rdi], 0
0x18006818c  mov     [rsp+28h+Sid], 0
0x180068195  lea     rdx, [rsp+28h+Sid]; void *
0x18006819a  mov     rcx, [rsp+28h+arg_8]; this
0x18006819f  call    ?GetPackageSidFromProcessHandle@CallerIdentity@@YAJPEAXPEAPEAX@Z; CallerIdentity::GetPackageSidFromProcessHandle(void *,void * *)
0x1800681a4  mov     ebx, eax
0x1800681a6  test    eax, eax
0x1800681a8  js      short loc_1800681D3
0x1800681aa  mov     rdx, rdi; StringSid
0x1800681ad  mov     rcx, [rsp+28h+Sid]; Sid
0x1800681b2  call    cs:__imp_ConvertSidToStringSidW
0x1800681b8  test    eax, eax
0x1800681ba  jz      short loc_1800681C0
0x1800681bc  xor     ebx, ebx
0x1800681be  jmp     short loc_1800681C7
0x1800681c0  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1800681c5  mov     ebx, eax
0x1800681c7  mov     rcx, [rsp+28h+Sid]; hMem
0x1800681cc  call    cs:__imp_LocalFree
0x1800681d2  nop
0x1800681d3  lea     rcx, [rsp+28h+arg_8]
0x1800681d8  call    ??1?$CTSmartObj@PEAXV?$CAutoHandle_Policy@PEAX@@@@QEAA@XZ; CTSmartObj<void *,CAutoHandle_Policy<void *>>::~CTSmartObj<void *,CAutoHandle_Policy<void *>>(void)
0x1800681dd  nop
0x1800681de  mov     eax, ebx
0x1800681e0  mov     rbx, [rsp+28h+arg_10]
0x1800681e5  add     rsp, 20h
0x1800681e9  pop     rdi
0x1800681ea  retn
```
