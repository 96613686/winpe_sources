# FltpTelemetryLegacyFiltersSafe

- ea: `0x1800236c8`
- end: `0x1800238bc`
- name: `FltpTelemetryLegacyFiltersSafe`
- size: `500`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x180052114`

## callees

- `0x180009f20`
- `0x1800236c8`
- `0x180024800`
- `0x180054e50`

## import_xrefs

- `ntoskrnl!IoGetStackLimits` at `0x18002386d`
- `ntoskrnl!IoGetStackLimits` at `0x18002386d`
- `ntoskrnl!ZwClose` at `0x180023830`
- `ntoskrnl!ZwClose` at `0x180023840`
- `ntoskrnl!ZwClose` at `0x180023830`
- `ntoskrnl!ZwClose` at `0x180023840`
- `ntoskrnl!ZwOpenKey` at `0x180023752`
- `ntoskrnl!ZwOpenKey` at `0x180023752`
- `ntoskrnl!ZwCreateKey` at `0x180023808`
- `ntoskrnl!ZwCreateKey` at `0x180023808`

## pseudocode

```c
void __fastcall FltpTelemetryLegacyFiltersSafe(__int64 a1, signed __int32 a2)
{
  signed __int32 v4; // ecx
  unsigned int v5; // eax
  unsigned int v6; // eax
  HANDLE Handle; // [rsp+40h] [rbp-49h] BYREF
  void *KeyHandle; // [rsp+48h] [rbp-41h] BYREF
  unsigned __int64 HighLimit; // [rsp+50h] [rbp-39h] BYREF
  _QWORD v10[2]; // [rsp+58h] [rbp-31h] BYREF
  OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+68h] [rbp-21h] BYREF
  __int128 v12; // [rsp+98h] [rbp+Fh] BYREF
  _OWORD v13[2]; // [rsp+A8h] [rbp+1Fh]

  v4 = _InterlockedExchangeAdd(&dword_18004053C, 0);
  if ( v4 < a2 )
  {
    _InterlockedCompareExchange(&dword_18004053C, a2, v4);
    if ( !v4 )
    {
      *(_QWORD *)&ObjectAttributes.Length = 48;
      KeyHandle = 0;
      ObjectAttributes.RootDirectory = 0;
      *(_QWORD *)&ObjectAttributes.Attributes = 576;
      ObjectAttributes.ObjectName = &DestinationString;
      *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
      v5 = ZwOpenKey(&KeyHandle, 0x20006u, &ObjectAttributes);
      if ( (int)FltpDbgStatus(v5, "minkernel\\fs\\filtermgr\\filter\\telemetrysup.c", 2349, 0) >= 0 )
      {
        v10[1] = &v12;
        v12 = *(_OWORD *)L"LegacyFiltersPresent";
        ObjectAttributes.RootDirectory = KeyHandle;
        v13[0] = *(_OWORD *)L"ltersPresent";
        v10[0] = 2752552;
        *(_OWORD *)((char *)v13 + 10) = *(_OWORD *)L"Present";
        Handle = 0;
        ObjectAttributes.Length = 48;
        *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
        ObjectAttributes.Attributes = 576;
        ObjectAttributes.ObjectName = (PUNICODE_STRING)v10;
        v6 = ZwCreateKey(&Handle, 0x20006u, &ObjectAttributes, 0, 0, 1u, 0);
        if ( (int)FltpDbgStatus(v6, "minkernel\\fs\\filtermgr\\filter\\telemetrysup.c", 2366, 0) >= 0 )
          ZwClose(Handle);
        ZwClose(KeyHandle);
      }
    }
  }
  if ( (unsigned int)dword_18003E018 > 5 )
  {
    HighLimit = 0;
    Handle = 0;
    IoGetStackLimits((PULONG_PTR)&Handle, &HighLimit);
    if ( (unsigned __int64)((char *)&HighLimit - (_BYTE *)Handle) >= 0x200 )
      FltpTelemetryLegacyFilters(a1, (unsigned int)a2);
    else
      _InterlockedIncrement(&dword_180040530);
  }
}

```

## disassembly

```asm
0x1800236c8  mov     [rsp-8+arg_10], rbx
0x1800236cd  push    rbp
0x1800236ce  push    rsi
0x1800236cf  push    rdi
0x1800236d0  lea     rbp, [rsp-47h]
0x1800236d5  sub     rsp, 0D0h
0x1800236dc  mov     rax, cs:__security_cookie
0x1800236e3  xor     rax, rsp
0x1800236e6  mov     [rbp+57h+var_18], rax
0x1800236ea  mov     rdi, rcx
0x1800236ed  mov     ebx, edx
0x1800236ef  xor     ecx, ecx
0x1800236f1  lock xadd cs:dword_18004053C, ecx
0x1800236f9  cmp     ecx, edx
0x1800236fb  jge     loc_18002384C
0x180023701  mov     eax, ecx
0x180023703  lock cmpxchg cs:dword_18004053C, ebx
0x18002370b  test    ecx, ecx
0x18002370d  jnz     loc_18002384C
0x180023713  xor     eax, eax
0x180023715  mov     qword ptr [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x18002371d  mov     [rbp+57h+KeyHandle], rax
0x180023721  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x180023725  mov     [rbp+57h+ObjectAttributes.RootDirectory], rax
0x180023729  lea     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x18002372d  lea     rax, DestinationString
0x180023734  mov     qword ptr [rbp+57h+ObjectAttributes.Attributes], 240h
0x18002373c  xorps   xmm0, xmm0
0x18002373f  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x180023743  mov     edx, 20006h; DesiredAccess
0x180023748  mov     esi, 92Dh
0x18002374d  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x180023752  call    cs:__imp_ZwOpenKey
0x180023759  nop     dword ptr [rax+rax+00h]
0x18002375e  xor     r9d, r9d
0x180023761  lea     rdx, aMinkernelFsFil_13; "minkernel\\fs\\filtermgr\\filter\\telem"...
0x180023768  mov     ecx, eax
0x18002376a  mov     r8d, esi
0x18002376d  call    FltpDbgStatus
0x180023772  test    eax, eax
0x180023774  js      loc_18002384C
0x18002377a  movups  xmm0, xmmword ptr cs:aLegacyfiltersp; "LegacyFiltersPresent"
0x180023781  lea     rax, [rbp+57h+var_48]
0x180023785  mov     [rsp+0E0h+Disposition], 0; Disposition
0x18002378e  movups  xmm1, xmmword ptr cs:aLegacyfiltersp+10h; "ltersPresent"
0x180023795  mov     [rbp+57h+var_80], rax
0x180023799  xor     r9d, r9d; TitleIndex
0x18002379c  mov     rax, [rbp+57h+KeyHandle]
0x1800237a0  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x1800237a4  movups  [rbp+57h+var_48], xmm0
0x1800237a8  mov     [rbp+57h+ObjectAttributes.RootDirectory], rax
0x1800237ac  lea     rax, [rbp+57h+var_88]
0x1800237b0  movups  xmm0, xmmword ptr cs:aLegacyfiltersp+1Ah; "Present"
0x1800237b7  mov     [rsp+0E0h+CreateOptions], 1; CreateOptions
0x1800237bf  mov     edx, 20006h; DesiredAccess
0x1800237c4  movups  xmmword ptr [rbp+57h+var_38], xmm1
0x1800237c8  lea     rcx, [rbp+57h+Handle]; KeyHandle
0x1800237cc  mov     [rbp+57h+var_88], 2A0028h
0x1800237d4  movups  xmmword ptr [rbp+57h+var_38+0Ah], xmm0
0x1800237d8  mov     [rbp+57h+Handle], 0
0x1800237e0  mov     esi, 93Eh
0x1800237e5  xorps   xmm0, xmm0
0x1800237e8  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x1800237ef  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x1800237f4  mov     [rbp+57h+ObjectAttributes.Attributes], 240h
0x1800237fb  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x1800237ff  mov     [rsp+0E0h+Class], 0; Class
0x180023808  call    cs:__imp_ZwCreateKey
0x18002380f  nop     dword ptr [rax+rax+00h]
0x180023814  xor     r9d, r9d
0x180023817  lea     rdx, aMinkernelFsFil_13; "minkernel\\fs\\filtermgr\\filter\\telem"...
0x18002381e  mov     ecx, eax
0x180023820  mov     r8d, esi
0x180023823  call    FltpDbgStatus
0x180023828  test    eax, eax
0x18002382a  js      short loc_18002383C
0x18002382c  mov     rcx, [rbp+57h+Handle]; Handle
0x180023830  call    cs:__imp_ZwClose
0x180023837  nop     dword ptr [rax+rax+00h]
0x18002383c  mov     rcx, [rbp+57h+KeyHandle]; Handle
0x180023840  call    cs:__imp_ZwClose
0x180023847  nop     dword ptr [rax+rax+00h]
0x18002384c  cmp     cs:dword_18003E018, 5
0x180023853  jbe     short loc_18002389C
0x180023855  lea     rdx, [rbp+57h+HighLimit]; HighLimit
0x180023859  mov     [rbp+57h+HighLimit], 0
0x180023861  lea     rcx, [rbp+57h+Handle]; LowLimit
0x180023865  mov     [rbp+57h+Handle], 0
0x18002386d  call    cs:__imp_IoGetStackLimits
0x180023874  nop     dword ptr [rax+rax+00h]
0x180023879  lea     rax, [rbp+57h+HighLimit]
0x18002387d  sub     rax, [rbp+57h+Handle]
0x180023881  cmp     rax, 200h
0x180023887  jnb     short loc_180023892
0x180023889  lock inc cs:dword_180040530
0x180023890  jmp     short loc_18002389C
0x180023892  mov     edx, ebx
0x180023894  mov     rcx, rdi
0x180023897  call    FltpTelemetryLegacyFilters
0x18002389c  mov     rcx, [rbp+57h+var_18]
0x1800238a0  xor     rcx, rsp; StackCookie
0x1800238a3  call    __security_check_cookie
0x1800238a8  mov     rbx, [rsp+0E0h+arg_10]
0x1800238b0  add     rsp, 0D0h
0x1800238b7  pop     rdi
0x1800238b8  pop     rsi
0x1800238b9  pop     rbp
0x1800238ba  retn
```
