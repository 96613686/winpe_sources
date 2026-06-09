# USBSTOR_GetWriteProtectSetting

- ea: `0x140025630`
- end: `0x140025731`
- name: `USBSTOR_GetWriteProtectSetting`
- size: `257`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x140004ed0`
- `0x1400250c0`

## callees

- `0x140013950`
- `0x140013d40`
- `0x140025630`

## import_xrefs

- `ntoskrnl!RtlQueryRegistryValuesEx` at `0x140025720`
- `ntoskrnl!RtlQueryRegistryValuesEx` at `0x140025720`
- `ntoskrnl!RtlGetVersion` at `0x140025680`
- `ntoskrnl!RtlGetVersion` at `0x140025680`

## string_xrefs

- `0x1400256db`: `WriteProtect`
- `0x140025709`: `\Registry\Machine\System\CurrentControlSet\Control\StorageDevicePolicies`

## pseudocode

```c
bool __fastcall USBSTOR_GetWriteProtectSetting(__int64 a1)
{
  bool result; // al
  int v3; // [rsp+30h] [rbp-1B8h] BYREF
  _QWORD v4[14]; // [rsp+40h] [rbp-1A8h] BYREF
  _DWORD VersionInformation[72]; // [rsp+B0h] [rbp-138h] BYREF

  memset(&VersionInformation[1], 0, 0x118u);
  VersionInformation[0] = 284;
  v3 = 0;
  if ( RtlGetVersion((PRTL_OSVERSIONINFOW)VersionInformation) >= 0 && BYTE2(VersionInformation[70]) == 1 )
  {
    memset(v4, 0, sizeof(v4));
    LODWORD(v4[1]) = 292;
    v4[2] = L"WriteProtect";
    LODWORD(v4[4]) = 67108868;
    v4[3] = &v3;
    v4[5] = 0;
    LODWORD(v4[6]) = 0;
    RtlQueryRegistryValuesEx(0, L"\\Registry\\Machine\\System\\CurrentControlSet\\Control\\StorageDevicePolicies", v4);
  }
  result = v3 != 0;
  *(_BYTE *)(a1 + 1824) = v3 != 0;
  return result;
}

```

## disassembly

```asm
0x140025630  mov     [rsp+arg_8], rbx
0x140025635  push    rdi
0x140025636  sub     rsp, 1E0h
0x14002563d  mov     rax, cs:__security_cookie
0x140025644  xor     rax, rsp
0x140025647  mov     [rsp+1E8h+var_18], rax
0x14002564f  mov     rbx, rcx
0x140025652  xor     edx, edx; Val
0x140025654  lea     rcx, [rsp+1E8h+VersionInformation.dwMajorVersion]; void *
0x14002565c  mov     r8d, 118h; Size
0x140025662  call    memset
0x140025667  xor     edi, edi
0x140025669  mov     [rsp+1E8h+VersionInformation.dwOSVersionInfoSize], 11Ch
0x140025674  lea     rcx, [rsp+1E8h+VersionInformation]; lpVersionInformation
0x14002567c  mov     [rsp+1E8h+var_1B8], edi
0x140025680  call    cs:__imp_RtlGetVersion
0x140025687  nop     dword ptr [rax+rax+00h]
0x14002568c  test    eax, eax
0x14002568e  jns     short loc_1400256BF
0x140025690  cmp     [rsp+1E8h+var_1B8], edi
0x140025694  setnz   al
0x140025697  mov     [rbx+720h], al
0x14002569d  mov     rcx, [rsp+1E8h+var_18]
0x1400256a5  xor     rcx, rsp; StackCookie
0x1400256a8  call    __security_check_cookie
0x1400256ad  mov     rbx, [rsp+1E8h+arg_8]
0x1400256b5  add     rsp, 1E0h
0x1400256bc  pop     rdi
0x1400256bd  retn
0x1400256bf  cmp     [rsp+1E8h+var_1E], 1
0x1400256c7  jnz     short loc_140025690
0x1400256c9  xor     edx, edx; Val
0x1400256cb  lea     rcx, [rsp+1E8h+var_1A8]; void *
0x1400256d0  mov     r8d, 70h ; 'p'; Size
0x1400256d6  call    memset
0x1400256db  lea     rax, aWriteprotect; "WriteProtect"
0x1400256e2  mov     [rsp+1E8h+var_1A0], 124h
0x1400256ea  mov     [rsp+1E8h+var_198], rax
0x1400256ef  lea     r8, [rsp+1E8h+var_1A8]
0x1400256f4  lea     rax, [rsp+1E8h+var_1B8]
0x1400256f9  mov     [rsp+1E8h+var_188], 4000004h
0x140025701  xor     r9d, r9d
0x140025704  mov     [rsp+1E8h+var_190], rax
0x140025709  lea     rdx, aRegistryMachin; "\\Registry\\Machine\\System\\CurrentCon"...
0x140025710  mov     [rsp+1E8h+var_180], rdi
0x140025715  xor     ecx, ecx
0x140025717  mov     [rsp+1E8h+var_178], edi
0x14002571b  mov     [rsp+1E8h+var_1C8], rdi
0x140025720  call    cs:__imp_RtlQueryRegistryValuesEx
0x140025727  nop     dword ptr [rax+rax+00h]
0x14002572c  jmp     loc_140025690
```
