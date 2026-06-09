# Streaming::StreamFaultWriterWorker::StreamFaultWriterWorker(long &)

- ea: `0x140004fec`
- end: `0x140005284`
- name: `??0StreamFaultWriterWorker@Streaming@@AEAA@AEAJ@Z`
- size: `664`
- prototype: `char *__fastcall(char *StartContext, int *)`
- caller_count: `1`
- callee_count: `2`
- tags: `reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x140006158`

## callees

- `0x140004fec`
- `0x140006864`

## import_xrefs

- `ntoskrnl!ZwQueryValueKey` at `0x14000522a`
- `ntoskrnl!ZwQueryValueKey` at `0x14000522a`
- `ntoskrnl!ZwCreateKey` at `0x1400051c8`
- `ntoskrnl!ZwCreateKey` at `0x1400051c8`
- `ntoskrnl!KeInitializeSemaphore` at `0x1400050e3`
- `ntoskrnl!KeInitializeSemaphore` at `0x1400050fe`
- `ntoskrnl!KeInitializeSemaphore` at `0x1400050e3`
- `ntoskrnl!KeInitializeSemaphore` at `0x1400050fe`
- `ntoskrnl!ExInitializeResourceLite` at `0x140005063`
- `ntoskrnl!ExInitializeResourceLite` at `0x1400050b4`
- `ntoskrnl!ExInitializeResourceLite` at `0x140005063`
- `ntoskrnl!ExInitializeResourceLite` at `0x1400050b4`
- `ntoskrnl!RtlInitUnicodeString` at `0x140005159`
- `ntoskrnl!RtlInitUnicodeString` at `0x140005177`
- `ntoskrnl!RtlInitUnicodeString` at `0x140005159`
- `ntoskrnl!RtlInitUnicodeString` at `0x140005177`
- `ntoskrnl!ExFreePoolWithTag` at `0x140005258`
- `ntoskrnl!ExFreePoolWithTag` at `0x140005258`
- `ntoskrnl!ExAllocatePool2` at `0x140005042`
- `ntoskrnl!ExAllocatePool2` at `0x14000509c`
- `ntoskrnl!ExAllocatePool2` at `0x1400051f7`
- `ntoskrnl!ExAllocatePool2` at `0x140005042`
- `ntoskrnl!ExAllocatePool2` at `0x14000509c`
- `ntoskrnl!ExAllocatePool2` at `0x1400051f7`

## string_xrefs

- `0x14000512d`: `\Registry\Machine\Software\Microsoft\AppV\Client\Streaming`
- `0x140005168`: `WriteQueueMaxSize`

## pseudocode

```c
char *__fastcall Streaming::StreamFaultWriterWorker::StreamFaultWriterWorker(char *StartContext, int *a2)
{
  struct _ERESOURCE *Pool2; // rax
  NTSTATUS v5; // esi
  NTSTATUS v6; // edi
  struct _ERESOURCE *v7; // rax
  ULONG v8; // esi
  _DWORD *v9; // rdi
  struct _UNICODE_STRING ValueName; // [rsp+40h] [rbp-19h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+50h] [rbp-9h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+60h] [rbp+7h] BYREF
  ULONG ResultLength; // [rsp+C0h] [rbp+67h] BYREF
  void *KeyHandle; // [rsp+D0h] [rbp+77h] BYREF

  *(_DWORD *)StartContext = 0;
  *((_QWORD *)StartContext + 1) = 0;
  *((_QWORD *)StartContext + 2) = 0;
  *((_QWORD *)StartContext + 4) = StartContext + 8;
  *((_QWORD *)StartContext + 3) = StartContext + 8;
  *((_DWORD *)StartContext + 10) = 2003199603;
  *((_QWORD *)StartContext + 6) = 0;
  Pool2 = (struct _ERESOURCE *)ExAllocatePool2(64, 104, 2003199603);
  *((_QWORD *)StartContext + 6) = Pool2;
  v5 = -1073741670;
  if ( Pool2 )
    v6 = ExInitializeResourceLite(Pool2);
  else
    v6 = -1073741670;
  *((_QWORD *)StartContext + 7) = 0;
  *((_QWORD *)StartContext + 8) = 0;
  *((_QWORD *)StartContext + 9) = 0;
  *((_QWORD *)StartContext + 10) = 0;
  *((_QWORD *)StartContext + 11) = 0;
  StartContext[96] = 1;
  *((_DWORD *)StartContext + 26) = 2003199603;
  *((_QWORD *)StartContext + 14) = 0;
  v7 = (struct _ERESOURCE *)ExAllocatePool2(64, 104, 2003199603);
  *((_QWORD *)StartContext + 14) = v7;
  if ( v7 )
    v5 = ExInitializeResourceLite(v7);
  StartContext[120] = 0;
  *((_QWORD *)StartContext + 16) = 0;
  *((_QWORD *)StartContext + 17) = 0;
  KeInitializeSemaphore((PRKSEMAPHORE)(StartContext + 144), 0, 0xFFFF);
  KeInitializeSemaphore((PRKSEMAPHORE)(StartContext + 176), 0, 0xFFFF);
  *((_DWORD *)StartContext + 53) = 2;
  if ( v6 >= 0 )
  {
    if ( v5 >= 0 )
      v6 = appv::shared::kernel::ThreadPool<kernel_std::shared_ptr<Streaming::StreamFaultWriter>,Streaming::StreamFaultWriterTagInfo>::InitializeThreadPool(StartContext);
    else
      v6 = v5;
  }
  *a2 = v6;
  *((_DWORD *)StartContext + 54) = 1500;
  KeyHandle = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  DestinationString = 0;
  RtlInitUnicodeString(&DestinationString, L"\\Registry\\Machine\\Software\\Microsoft\\AppV\\Client\\Streaming");
  ValueName = 0;
  RtlInitUnicodeString(&ValueName, L"WriteQueueMaxSize");
  ObjectAttributes.ObjectName = &DestinationString;
  ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 576;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  if ( ZwCreateKey(&KeyHandle, 1u, &ObjectAttributes, 0, 0, 1u, 0) >= 0 )
  {
    v8 = (ValueName.Length + 33) & 0xFFFFFFFC;
    if ( v8 )
    {
      v9 = (_DWORD *)ExAllocatePool2(256, v8, 2003199603);
      if ( !v9 )
        return StartContext;
    }
    else
    {
      v9 = 0;
    }
    ResultLength = 0;
    if ( ZwQueryValueKey(KeyHandle, &ValueName, KeyValueFullInformation, v9, v8, &ResultLength) >= 0 )
    {
      if ( v9[1] == 4 )
        *((_DWORD *)StartContext + 54) = *(_DWORD *)((char *)v9 + (unsigned int)v9[2]);
    }
    else if ( !v9 )
    {
      return StartContext;
    }
    ExFreePoolWithTag(v9, 0);
  }
  return StartContext;
}

```

## disassembly

```asm
0x140004fec  mov     [rsp-8+arg_8], rbx
0x140004ff1  mov     [rsp-8+arg_18], rsi
0x140004ff6  push    rbp
0x140004ff7  push    rdi
0x140004ff8  push    r12
0x140004ffa  push    r13
0x140004ffc  push    r14
0x140004ffe  lea     rbp, [rsp-37h]
0x140005003  sub     rsp, 90h
0x14000500a  lea     rax, [rcx+8]
0x14000500e  xor     r12d, r12d
0x140005011  mov     [rcx], r12d
0x140005014  mov     r14, rdx
0x140005017  mov     r13d, 77666673h
0x14000501d  mov     [rax], r12
0x140005020  mov     [rax+8], r12
0x140005024  mov     rbx, rcx
0x140005027  lea     edx, [r12+68h]
0x14000502c  mov     [rax+18h], rax
0x140005030  mov     [rax+10h], rax
0x140005034  mov     r8d, r13d
0x140005037  mov     [rcx+28h], r13d
0x14000503b  mov     [rcx+30h], r12
0x14000503f  lea     ecx, [rdx-28h]
0x140005042  call    cs:__imp_ExAllocatePool2
0x140005049  nop     dword ptr [rax+rax+00h]
0x14000504e  mov     [rbx+30h], rax
0x140005052  mov     esi, 0C000009Ah
0x140005057  test    rax, rax
0x14000505a  jnz     short loc_140005060
0x14000505c  mov     edi, esi
0x14000505e  jmp     short loc_140005071
0x140005060  mov     rcx, rax; Resource
0x140005063  call    cs:__imp_ExInitializeResourceLite
0x14000506a  nop     dword ptr [rax+rax+00h]
0x14000506f  mov     edi, eax
0x140005071  mov     edx, 68h ; 'h'
0x140005076  mov     [rbx+38h], r12
0x14000507a  mov     [rbx+40h], r12
0x14000507e  mov     r8d, r13d
0x140005081  mov     [rbx+48h], r12
0x140005085  mov     [rbx+50h], r12
0x140005089  mov     [rbx+58h], r12
0x14000508d  lea     ecx, [rdx-28h]
0x140005090  mov     byte ptr [rbx+60h], 1
0x140005094  mov     [rbx+68h], r13d
0x140005098  mov     [rbx+70h], r12
0x14000509c  call    cs:__imp_ExAllocatePool2
0x1400050a3  nop     dword ptr [rax+rax+00h]
0x1400050a8  mov     [rbx+70h], rax
0x1400050ac  test    rax, rax
0x1400050af  jz      short loc_1400050C2
0x1400050b1  mov     rcx, rax; Resource
0x1400050b4  call    cs:__imp_ExInitializeResourceLite
0x1400050bb  nop     dword ptr [rax+rax+00h]
0x1400050c0  mov     esi, eax
0x1400050c2  lea     rcx, [rbx+90h]; Semaphore
0x1400050c9  mov     [rbx+78h], r12b
0x1400050cd  xor     edx, edx; Count
0x1400050cf  mov     [rbx+80h], r12
0x1400050d6  mov     r8d, 0FFFFh; Limit
0x1400050dc  mov     [rbx+88h], r12
0x1400050e3  call    cs:__imp_KeInitializeSemaphore
0x1400050ea  nop     dword ptr [rax+rax+00h]
0x1400050ef  lea     rcx, [rbx+0B0h]; Semaphore
0x1400050f6  xor     edx, edx; Count
0x1400050f8  mov     r8d, 0FFFFh; Limit
0x1400050fe  call    cs:__imp_KeInitializeSemaphore
0x140005105  nop     dword ptr [rax+rax+00h]
0x14000510a  mov     dword ptr [rbx+0D4h], 2
0x140005114  test    edi, edi
0x140005116  js      short loc_14000512A
0x140005118  test    esi, esi
0x14000511a  jns     short loc_140005120
0x14000511c  mov     edi, esi
0x14000511e  jmp     short loc_14000512A
0x140005120  mov     rcx, rbx; StartContext
0x140005123  call    ?InitializeThreadPool@?$ThreadPool@V?$shared_ptr@VStreamFaultWriter@Streaming@@@kernel_std@@VStreamFaultWriterTagInfo@Streaming@@@kernel@shared@appv@@AEAAJXZ; appv::shared::kernel::ThreadPool<kernel_std::shared_ptr<Streaming::StreamFaultWriter>,Streaming::StreamFaultWriterTagInfo>::InitializeThreadPool(void)
0x140005128  mov     edi, eax
0x14000512a  mov     [r14], edi
0x14000512d  lea     rdx, aRegistryMachin_0; "\\Registry\\Machine\\Software\\Microsof"...
0x140005134  xorps   xmm0, xmm0
0x140005137  mov     dword ptr [rbx+0D8h], 5DCh
0x140005141  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x140005145  mov     [rbp+57h+KeyHandle], r12
0x140005149  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x14000514d  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x140005151  movups  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x140005155  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x140005159  call    cs:__imp_RtlInitUnicodeString
0x140005160  nop     dword ptr [rax+rax+00h]
0x140005165  xorps   xmm0, xmm0
0x140005168  lea     rdx, aWritequeuemaxs; "WriteQueueMaxSize"
0x14000516f  lea     rcx, [rbp+57h+ValueName]; DestinationString
0x140005173  movups  xmmword ptr [rbp+57h+ValueName.Length], xmm0
0x140005177  call    cs:__imp_RtlInitUnicodeString
0x14000517e  nop     dword ptr [rax+rax+00h]
0x140005183  mov     r14d, 1
0x140005189  mov     [rsp+0B0h+Disposition], r12; Disposition
0x14000518e  lea     rax, [rbp+57h+DestinationString]
0x140005192  mov     [rsp+0B0h+CreateOptions], r14d; CreateOptions
0x140005197  xorps   xmm0, xmm0
0x14000519a  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x14000519e  mov     edx, r14d; DesiredAccess
0x1400051a1  mov     [rsp+0B0h+Class], r12; Class
0x1400051a6  xor     r9d, r9d; TitleIndex
0x1400051a9  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x1400051b0  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x1400051b4  mov     [rbp+57h+ObjectAttributes.RootDirectory], r12
0x1400051b8  lea     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x1400051bc  mov     [rbp+57h+ObjectAttributes.Attributes], 240h
0x1400051c3  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x1400051c8  call    cs:__imp_ZwCreateKey
0x1400051cf  nop     dword ptr [rax+rax+00h]
0x1400051d4  test    eax, eax
0x1400051d6  js      loc_140005264
0x1400051dc  movzx   esi, [rbp+57h+ValueName.Length]
0x1400051e0  add     esi, 21h ; '!'
0x1400051e3  and     esi, 0FFFFFFFCh
0x1400051e6  ja      short loc_1400051ED
0x1400051e8  mov     rdi, r12
0x1400051eb  jmp     short loc_14000520B
0x1400051ed  mov     edx, esi
0x1400051ef  mov     r8d, r13d
0x1400051f2  mov     ecx, 100h
0x1400051f7  call    cs:__imp_ExAllocatePool2
0x1400051fe  nop     dword ptr [rax+rax+00h]
0x140005203  mov     rdi, rax
0x140005206  test    rax, rax
0x140005209  jz      short loc_140005264
0x14000520b  mov     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x14000520f  lea     rax, [rbp+57h+ResultLength]
0x140005213  mov     qword ptr [rsp+0B0h+CreateOptions], rax; ResultLength
0x140005218  lea     rdx, [rbp+57h+ValueName]; ValueName
0x14000521c  mov     r9, rdi; KeyValueInformation
0x14000521f  mov     dword ptr [rsp+0B0h+Class], esi; Length
0x140005223  mov     r8d, r14d; KeyValueInformationClass
0x140005226  mov     [rbp+57h+ResultLength], r12d
0x14000522a  call    cs:__imp_ZwQueryValueKey
0x140005231  nop     dword ptr [rax+rax+00h]
0x140005236  test    eax, eax
0x140005238  jns     short loc_140005241
0x14000523a  test    rdi, rdi
0x14000523d  jnz     short loc_140005253
0x14000523f  jmp     short loc_140005264
0x140005241  cmp     dword ptr [rdi+4], 4
0x140005245  jnz     short loc_140005253
0x140005247  mov     eax, [rdi+8]
0x14000524a  mov     ecx, [rax+rdi]
0x14000524d  mov     [rbx+0D8h], ecx
0x140005253  xor     edx, edx; Tag
0x140005255  mov     rcx, rdi; P
0x140005258  call    cs:__imp_ExFreePoolWithTag
0x14000525f  nop     dword ptr [rax+rax+00h]
0x140005264  lea     r11, [rsp+0B0h+var_20]
0x14000526c  mov     rax, rbx
0x14000526f  mov     rbx, [r11+38h]
0x140005273  mov     rsi, [r11+48h]
0x140005277  mov     rsp, r11
0x14000527a  pop     r14
0x14000527c  pop     r13
0x14000527e  pop     r12
0x140005280  pop     rdi
0x140005281  pop     rbp
0x140005282  retn
```
