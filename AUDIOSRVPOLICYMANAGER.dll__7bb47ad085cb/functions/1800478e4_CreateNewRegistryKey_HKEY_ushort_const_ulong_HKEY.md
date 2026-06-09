# CreateNewRegistryKey(HKEY__ *,ushort const *,ulong,HKEY__ * *)

- ea: `0x1800478e4`
- end: `0x1800479eb`
- name: `?CreateNewRegistryKey@@YAJPEAUHKEY__@@PEBGKPEAPEAU1@@Z`
- size: `263`
- prototype: `int(HKEY, const unsigned __int16 *, unsigned int, HKEY *)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18000e37c`

## callees

- `0x18000fea4`
- `0x18001039c`
- `0x1800109d0`
- `0x180010a00`
- `0x1800478e4`
- `0x180047ce0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800479a1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800479a1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800479d3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800479d3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180047999`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180047999`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180047966`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180047966`

## pseudocode

```c
__int64 __fastcall CreateNewRegistryKey(HKEY a1, const unsigned __int16 *a2, __int64 a3, HKEY *a4)
{
  signed int LastError; // eax
  __int64 v7; // r8
  unsigned __int16 *v8; // r9
  signed int v9; // ebx
  bool v10; // cc
  unsigned int v12; // [rsp+20h] [rbp-58h]
  struct _SECURITY_ATTRIBUTES v13; // [rsp+50h] [rbp-28h] BYREF
  PSID Sid; // [rsp+A0h] [rbp+28h] BYREF

  Sid = a1;
  memset(&v13, 0, sizeof(v13));
  v13.nLength = 24;
  LastError = DetermineLowRightsKeySecurityDescriptor(HKEY_CURRENT_USER, &v13.lpSecurityDescriptor);
  v9 = LastError;
  v10 = LastError <= 0;
  if ( !LastError )
  {
    LastError = SafeRegCreateKeyEx(HKEY_CURRENT_USER, a2, v7, v8, v12, 0xA001Fu, &v13, a4);
    v9 = LastError;
    v10 = LastError <= 0;
    if ( !LastError )
    {
      Sid = 0;
      if ( ConvertStringSidToSidW(L"LW", &Sid) )
      {
        v9 = SetRegistryKeyIntegrityLevel(*a4, Sid);
        if ( v9 < 0 )
          v9 = SetRegistryHandleIntegrityLevel(*a4, Sid);
        if ( Sid )
          LocalFree(Sid);
        goto LABEL_11;
      }
      LastError = GetLastError();
      v9 = LastError;
      v10 = LastError <= 0;
    }
  }
  if ( !v10 )
    v9 = (unsigned __int16)LastError | 0x80070000;
LABEL_11:
  operator delete(v13.lpSecurityDescriptor);
  v13.lpSecurityDescriptor = 0;
  if ( v9 < 0 && *a4 )
  {
    RegCloseKey(*a4);
    *a4 = 0;
  }
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x1800478e4  mov     [rsp-20h+Sid], rcx
0x1800478e9  push    rbp
0x1800478ea  push    rbx
0x1800478eb  push    rsi
0x1800478ec  push    rdi
0x1800478ed  mov     rbp, rsp
0x1800478f0  sub     rsp, 78h
0x1800478f4  xorps   xmm0, xmm0
0x1800478f7  mov     rsi, rdx
0x1800478fa  xor     eax, eax
0x1800478fc  lea     rdx, [rbp+var_28.lpSecurityDescriptor]; void **
0x180047900  movups  xmmword ptr [rbp-28h], xmm0
0x180047904  mov     rcx, 0FFFFFFFF80000001h; hKey
0x18004790b  mov     [rbp+var_28.nLength], 18h
0x180047912  mov     rdi, r9
0x180047915  mov     qword ptr [rbp+var_28.bInheritHandle], rax
0x180047919  call    ?DetermineLowRightsKeySecurityDescriptor@@YAJPEAUHKEY__@@PEAPEAX@Z; DetermineLowRightsKeySecurityDescriptor(HKEY__ *,void * *)
0x18004791e  mov     ebx, eax
0x180047920  test    eax, eax
0x180047922  jnz     loc_1800479AB
0x180047928  lea     rax, [rbp+var_28]
0x18004792c  mov     [rsp+78h+var_40], rdi; HKEY *
0x180047931  mov     [rsp+78h+var_48], rax; LPSECURITY_ATTRIBUTES
0x180047936  mov     rdx, rsi; unsigned __int16 *
0x180047939  mov     rcx, 0FFFFFFFF80000001h; HKEY
0x180047940  mov     [rsp+78h+samDesired], 0A001Fh; samDesired
0x180047948  call    ?SafeRegCreateKeyEx@@YAJPEAUHKEY__@@PEBGKPEAGKKPEAU_SECURITY_ATTRIBUTES@@PEAPEAU1@PEAK@Z; SafeRegCreateKeyEx(HKEY__ *,ushort const *,ulong,ushort *,ulong,ulong,_SECURITY_ATTRIBUTES *,HKEY__ * *,ulong *)
0x18004794d  mov     ebx, eax
0x18004794f  test    eax, eax
0x180047951  jnz     short loc_1800479AB
0x180047953  lea     rdx, [rbp+Sid]; Sid
0x180047957  mov     [rbp+Sid], 0
0x18004795f  lea     rcx, StringSid; "LW"
0x180047966  call    cs:__imp_ConvertStringSidToSidW
0x18004796c  test    eax, eax
0x18004796e  jz      short loc_1800479A1
0x180047970  mov     rdx, [rbp+Sid]; pSid
0x180047974  mov     rcx, [rdi]; hKey
0x180047977  call    ?SetRegistryKeyIntegrityLevel@@YAJPEAUHKEY__@@PEAX@Z; SetRegistryKeyIntegrityLevel(HKEY__ *,void *)
0x18004797c  mov     ebx, eax
0x18004797e  test    eax, eax
0x180047980  jns     short loc_180047990
0x180047982  mov     rdx, [rbp+Sid]; void *
0x180047986  mov     rcx, [rdi]; Handle
0x180047989  call    ?SetRegistryHandleIntegrityLevel@@YAJPEAUHKEY__@@PEAX@Z; SetRegistryHandleIntegrityLevel(HKEY__ *,void *)
0x18004798e  mov     ebx, eax
0x180047990  mov     rcx, [rbp+Sid]; hMem
0x180047994  test    rcx, rcx
0x180047997  jz      short loc_1800479B6
0x180047999  call    cs:__imp_LocalFree
0x18004799f  jmp     short loc_1800479B6
0x1800479a1  call    cs:__imp_GetLastError
0x1800479a7  mov     ebx, eax
0x1800479a9  test    eax, eax
0x1800479ab  jle     short loc_1800479B6
0x1800479ad  movzx   ebx, ax
0x1800479b0  or      ebx, 80070000h
0x1800479b6  mov     rcx, [rbp+var_28.lpSecurityDescriptor]; void *
0x1800479ba  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800479bf  mov     [rbp+var_28.lpSecurityDescriptor], 0
0x1800479c7  test    ebx, ebx
0x1800479c9  jns     short loc_1800479E0
0x1800479cb  mov     rcx, [rdi]; hKey
0x1800479ce  test    rcx, rcx
0x1800479d1  jz      short loc_1800479E0
0x1800479d3  call    cs:__imp_RegCloseKey
0x1800479d9  mov     qword ptr [rdi], 0
0x1800479e0  mov     eax, ebx
0x1800479e2  add     rsp, 78h
0x1800479e6  pop     rdi
0x1800479e7  pop     rsi
0x1800479e8  pop     rbx
0x1800479e9  pop     rbp
0x1800479ea  retn
```
