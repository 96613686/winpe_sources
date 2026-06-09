# WerpCreateRegistryKey

- ea: `0x140059550`
- end: `0x140059687`
- name: `WerpCreateRegistryKey`
- size: `311`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x140058984`

## callees

- `0x140059550`

## import_xrefs

- `ntoskrnl!DbgPrintEx` at `0x140059624`
- `ntoskrnl!DbgPrintEx` at `0x14005965d`
- `ntoskrnl!DbgPrintEx` at `0x140059624`
- `ntoskrnl!DbgPrintEx` at `0x14005965d`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400595a3`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400595a3`
- `ntoskrnl!ZwCreateKey` at `0x1400595fb`
- `ntoskrnl!ZwCreateKey` at `0x1400595fb`

## string_xrefs

- `0x140059617`: `WERLIVEKERNELREPORTING:%u: ERROR ZwCreateKey failed with scode 0x%x\n`

## pseudocode

```c
__int64 __fastcall WerpCreateRegistryKey(
        void *a1,
        const WCHAR *a2,
        ACCESS_MASK a3,
        char a4,
        PHANDLE KeyHandle,
        bool *a6)
{
  void **v9; // rbx
  NTSTATUS v10; // eax
  unsigned int v11; // ebx
  struct _UNICODE_STRING DestinationString; // [rsp+40h] [rbp-40h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+50h] [rbp-30h] BYREF
  ULONG Disposition; // [rsp+A8h] [rbp+28h] BYREF

  Disposition = 0;
  DestinationString = 0;
  memset(&ObjectAttributes, 0, 44);
  if ( a2 && (v9 = KeyHandle) != 0 )
  {
    RtlInitUnicodeString(&DestinationString, a2);
    ObjectAttributes.Length = 48;
    ObjectAttributes.ObjectName = &DestinationString;
    ObjectAttributes.RootDirectory = a1;
    ObjectAttributes.Attributes = 576;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    v10 = ZwCreateKey(v9, a3, &ObjectAttributes, 0, 0, a4 != 0, &Disposition);
    v11 = v10;
    if ( v10 >= 0 )
    {
      if ( a6 )
        *a6 = Disposition == 1;
      return 0;
    }
    else
    {
      DbgPrintEx(0x96u, 0, "WERLIVEKERNELREPORTING:%u: ERROR ZwCreateKey failed with scode 0x%x\n", 104, v10);
    }
    return v11;
  }
  else
  {
    DbgPrintEx(0x96u, 0, "WERLIVEKERNELREPORTING:%u: ERROR Invalid params\n", 81);
    return 3221225485LL;
  }
}

```

## disassembly

```asm
0x140059550  mov     [rsp-18h+arg_0], rbx
0x140059555  mov     [rsp-18h+arg_10], rsi
0x14005955a  push    rbp
0x14005955b  push    rdi
0x14005955c  push    r14
0x14005955e  mov     rbp, rsp
0x140059561  sub     rsp, 80h
0x140059568  xorps   xmm0, xmm0
0x14005956b  xor     eax, eax
0x14005956d  mov     [rbp+arg_8], eax
0x140059570  mov     dil, r9b
0x140059573  mov     esi, r8d
0x140059576  mov     r14, rcx
0x140059579  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x14005957d  movups  xmmword ptr [rbp+ObjectAttributes+1Ch], xmm0
0x140059581  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x140059585  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x140059589  test    rdx, rdx
0x14005958c  jz      loc_14005964A
0x140059592  mov     rbx, [rbp+KeyHandle]
0x140059596  test    rbx, rbx
0x140059599  jz      loc_14005964A
0x14005959f  lea     rcx, [rbp+DestinationString]; DestinationString
0x1400595a3  call    cs:__imp_RtlInitUnicodeString
0x1400595aa  nop     dword ptr [rax+rax+00h]
0x1400595af  lea     rax, [rbp+DestinationString]
0x1400595b3  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x1400595ba  mov     [rbp+ObjectAttributes.ObjectName], rax
0x1400595be  lea     rcx, [rbp+arg_8]
0x1400595c2  xor     eax, eax
0x1400595c4  mov     [rsp+80h+Disposition], rcx; Disposition
0x1400595c9  xorps   xmm0, xmm0
0x1400595cc  mov     [rbp+ObjectAttributes.RootDirectory], r14
0x1400595d0  test    dil, dil
0x1400595d3  mov     [rbp+ObjectAttributes.Attributes], 240h
0x1400595da  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x1400595de  mov     edx, esi; DesiredAccess
0x1400595e0  setnz   al
0x1400595e3  mov     rcx, rbx; KeyHandle
0x1400595e6  mov     [rsp+80h+CreateOptions], eax; CreateOptions
0x1400595ea  xor     r9d, r9d; TitleIndex
0x1400595ed  mov     [rsp+80h+Class], 0; Class
0x1400595f6  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x1400595fb  call    cs:__imp_ZwCreateKey
0x140059602  nop     dword ptr [rax+rax+00h]
0x140059607  mov     ebx, eax
0x140059609  test    eax, eax
0x14005960b  jns     short loc_140059632
0x14005960d  mov     r9d, 68h ; 'h'
0x140059613  mov     dword ptr [rsp+80h+Class], eax
0x140059617  lea     r8, aWerlivekernelr; "WERLIVEKERNELREPORTING:%u: ERROR ZwCrea"...
0x14005961e  xor     edx, edx; Level
0x140059620  lea     ecx, [r9+2Eh]; ComponentId
0x140059624  call    cs:__imp_DbgPrintEx
0x14005962b  nop     dword ptr [rax+rax+00h]
0x140059630  jmp     short loc_140059646
0x140059632  mov     rcx, [rbp+arg_28]
0x140059636  test    rcx, rcx
0x140059639  jz      short loc_140059644
0x14005963b  cmp     [rbp+arg_8], 1
0x14005963f  setz    al
0x140059642  mov     [rcx], al
0x140059644  xor     ebx, ebx
0x140059646  mov     eax, ebx
0x140059648  jmp     short loc_14005966E
0x14005964a  mov     r9d, 51h ; 'Q'
0x140059650  lea     r8, aWerlivekernelr_23; "WERLIVEKERNELREPORTING:%u: ERROR Invali"...
0x140059657  xor     edx, edx; Level
0x140059659  lea     ecx, [r9+45h]; ComponentId
0x14005965d  call    cs:__imp_DbgPrintEx
0x140059664  nop     dword ptr [rax+rax+00h]
0x140059669  mov     eax, 0C000000Dh
0x14005966e  lea     r11, [rsp+80h+var_s0]
0x140059676  mov     rbx, [r11+20h]
0x14005967a  mov     rsi, [r11+30h]
0x14005967e  mov     rsp, r11
0x140059681  pop     r14
0x140059683  pop     rdi
0x140059684  pop     rbp
0x140059685  retn
```
