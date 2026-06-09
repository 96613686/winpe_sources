# pSetupCreateKeyWorker

- ea: `0x14000b030`
- end: `0x14000b14e`
- name: `pSetupCreateKeyWorker`
- size: `286`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `reparse_path, authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x14000aeec`

## callees

- `0x14000aedc`
- `0x14000b030`
- `0x14000b2a8`

## import_xrefs

- `ntdll!NtCreateKey` at `0x14000b107`
- `ntdll!NtCreateKey` at `0x14000b107`
- `ntdll!RtlInitUnicodeString` at `0x14000b0a3`
- `ntdll!RtlInitUnicodeString` at `0x14000b0a3`
- `ntdll!RtlNtStatusToDosError` at `0x14000b113`
- `ntdll!RtlNtStatusToDosError` at `0x14000b113`

## pseudocode

```c
__int64 __fastcall pSetupCreateKeyWorker(
        void *a1,
        const WCHAR *a2,
        __int64 a3,
        ULONG a4,
        ACCESS_MASK DesiredAccess,
        __int64 a6,
        _QWORD *a7)
{
  void *v7; // rbx
  void *v10; // rsi
  ULONG v11; // edi
  ULONG v12; // eax
  int v13; // eax
  _UNICODE_STRING DestinationString; // [rsp+40h] [rbp-40h] BYREF
  _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+50h] [rbp-30h] BYREF
  void *KeyHandle; // [rsp+B0h] [rbp+30h] BYREF
  void *v18; // [rsp+C0h] [rbp+40h] BYREF

  KeyHandle = 0;
  v7 = 0;
  v18 = 0;
  v10 = a1;
  DestinationString = 0;
  memset(&ObjectAttributes, 0, 44);
  if ( (unsigned __int64)a1 + 0x80000000 <= 7 )
  {
    v12 = pSetupOpenPredefinedKey(a1, &v18);
    v7 = v18;
    v11 = v12;
    if ( v12 )
      goto LABEL_9;
  }
  else
  {
    v11 = 0;
  }
  RtlInitUnicodeString(&DestinationString, a2);
  ObjectAttributes.Length = 48;
  if ( v7 )
    v10 = v7;
  ObjectAttributes.RootDirectory = v10;
  ObjectAttributes.Attributes = (a4 & 8) != 0 ? 448 : 192;
  ObjectAttributes.ObjectName = &DestinationString;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v13 = NtCreateKey(&KeyHandle, DesiredAccess, &ObjectAttributes, 0, 0, a4, 0);
  if ( v13 >= 0 )
    *a7 = (int)KeyHandle;
  else
    v11 = RtlNtStatusToDosError(v13);
LABEL_9:
  if ( v7 )
    pSetupCloseKey(v7);
  return v11;
}

```

## disassembly

```asm
0x14000b030  mov     [rsp-28h+arg_8], rbx
0x14000b035  mov     [rsp-28h+arg_10], r8
0x14000b03a  push    rbp
0x14000b03b  push    rsi
0x14000b03c  push    rdi
0x14000b03d  push    r14
0x14000b03f  push    r15
0x14000b041  mov     rbp, rsp
0x14000b044  sub     rsp, 80h
0x14000b04b  xor     eax, eax
0x14000b04d  xorps   xmm0, xmm0
0x14000b050  mov     [rbp+KeyHandle], rax
0x14000b054  xor     ebx, ebx
0x14000b056  mov     eax, 80000000h
0x14000b05b  mov     [rbp+arg_10], rbx
0x14000b05f  add     rax, rcx
0x14000b062  mov     r14d, r9d
0x14000b065  mov     r15, rdx
0x14000b068  mov     rsi, rcx
0x14000b06b  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x14000b06f  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x14000b073  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x14000b077  movups  xmmword ptr [rbp+ObjectAttributes+1Ch], xmm0
0x14000b07b  cmp     rax, 7
0x14000b07f  jbe     short loc_14000B085
0x14000b081  xor     edi, edi
0x14000b083  jmp     short loc_14000B09C
0x14000b085  lea     rdx, [rbp+arg_10]
0x14000b089  call    pSetupOpenPredefinedKey
0x14000b08e  mov     rbx, [rbp+arg_10]
0x14000b092  mov     edi, eax
0x14000b094  test    eax, eax
0x14000b096  jnz     loc_14000B128
0x14000b09c  mov     rdx, r15; SourceString
0x14000b09f  lea     rcx, [rbp+DestinationString]; DestinationString
0x14000b0a3  call    cs:__imp_RtlInitUnicodeString
0x14000b0a9  mov     edx, [rbp+DesiredAccess]; DesiredAccess
0x14000b0ac  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x14000b0b0  mov     ecx, r14d
0x14000b0b3  mov     [rsp+80h+Disposition], 0; Disposition
0x14000b0bc  and     ecx, 8
0x14000b0bf  mov     [rsp+80h+CreateOptions], r14d; CreateOptions
0x14000b0c4  test    rbx, rbx
0x14000b0c7  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x14000b0ce  xorps   xmm0, xmm0
0x14000b0d1  mov     [rsp+80h+Class], 0; Class
0x14000b0da  cmovnz  rsi, rbx
0x14000b0de  neg     ecx
0x14000b0e0  lea     rcx, [rbp+KeyHandle]; KeyHandle
0x14000b0e4  mov     [rbp+ObjectAttributes.RootDirectory], rsi
0x14000b0e8  sbb     eax, eax
0x14000b0ea  xor     r9d, r9d; TitleIndex
0x14000b0ed  and     eax, 100h
0x14000b0f2  add     eax, 0C0h
0x14000b0f7  mov     [rbp+ObjectAttributes.Attributes], eax
0x14000b0fa  lea     rax, [rbp+DestinationString]
0x14000b0fe  mov     [rbp+ObjectAttributes.ObjectName], rax
0x14000b102  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x14000b107  call    cs:__imp_NtCreateKey
0x14000b10d  test    eax, eax
0x14000b10f  jns     short loc_14000B11D
0x14000b111  mov     ecx, eax; Status
0x14000b113  call    cs:__imp_RtlNtStatusToDosError
0x14000b119  mov     edi, eax
0x14000b11b  jmp     short loc_14000B128
0x14000b11d  mov     rax, [rbp+arg_30]
0x14000b121  movsxd  rcx, dword ptr [rbp+KeyHandle]
0x14000b125  mov     [rax], rcx
0x14000b128  test    rbx, rbx
0x14000b12b  jz      short loc_14000B135
0x14000b12d  mov     rcx, rbx
0x14000b130  call    pSetupCloseKey
0x14000b135  mov     rbx, [rsp+80h+arg_8]
0x14000b13d  mov     eax, edi
0x14000b13f  add     rsp, 80h
0x14000b146  pop     r15
0x14000b148  pop     r14
0x14000b14a  pop     rdi
0x14000b14b  pop     rsi
0x14000b14c  pop     rbp
0x14000b14d  retn
```
