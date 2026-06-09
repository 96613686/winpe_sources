# OpenVolumeHandle(bool,_UNICODE_STRING const *,void * *,ulong)

- ea: `0x14000b490`
- end: `0x14000b618`
- name: `?OpenVolumeHandle@@YAJ_NPEBU_UNICODE_STRING@@PEAPEAXK@Z`
- size: `392`
- prototype: `__int64 __fastcall(char, struct _UNICODE_STRING *, void **, ACCESS_MASK)`
- caller_count: `6`
- callee_count: `4`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x140005db4`
- `0x14000de58`
- `0x14000ea7c`
- `0x14000f97c`
- `0x1400127dc`
- `0x140020390`

## callees

- `0x140004ef0`
- `0x140005420`
- `0x14000b490`
- `0x14000b7f8`

## import_xrefs

- `ntdll!NtOpenFile` at `0x14000b55d`
- `ntdll!NtOpenFile` at `0x14000b55d`
- `ntdll!RtlGetThreadErrorMode` at `0x14000b4e1`
- `ntdll!RtlGetThreadErrorMode` at `0x14000b4e1`
- `ntdll!RtlSetThreadErrorMode` at `0x14000b4f0`
- `ntdll!RtlSetThreadErrorMode` at `0x14000b5c5`
- `ntdll!RtlSetThreadErrorMode` at `0x14000b5ee`
- `ntdll!RtlSetThreadErrorMode` at `0x14000b4f0`
- `ntdll!RtlSetThreadErrorMode` at `0x14000b5c5`
- `ntdll!RtlSetThreadErrorMode` at `0x14000b5ee`
- `ntdll!NtClose` at `0x14000b5b4`
- `ntdll!NtClose` at `0x14000b5b4`

## string_xrefs

- `0x14000b4c2`: `OpenVolumeHandle`

## pseudocode

```c
__int64 __fastcall OpenVolumeHandle(char a1, struct _UNICODE_STRING *a2, void **a3, ACCESS_MASK a4)
{
  ULONG ThreadErrorMode; // eax
  NTSTATUS v9; // eax
  char v10; // cl
  NTSTATUS v11; // eax
  unsigned int v12; // ebx
  bool v13; // zf
  _BYTE v15[8]; // [rsp+30h] [rbp-50h] BYREF
  int v16; // [rsp+38h] [rbp-48h]
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+40h] [rbp-40h] BYREF
  _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+50h] [rbp-30h] BYREF
  ULONG OldMode; // [rsp+B8h] [rbp+38h] BYREF
  char v20; // [rsp+BCh] [rbp+3Ch]
  void *FileHandle; // [rsp+C0h] [rbp+40h] BYREF

  *(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 8LL) = "OpenVolumeHandle";
  CHResultImp::CHResultImp((CHResultImp *)v15);
  *a3 = 0;
  v20 = 0;
  ThreadErrorMode = RtlGetThreadErrorMode();
  v9 = RtlSetThreadErrorMode(ThreadErrorMode | 0x10, &OldMode);
  v10 = v20;
  *(_QWORD *)&ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.ObjectName = a2;
  if ( v9 >= 0 )
    v10 = 1;
  *(_QWORD *)&ObjectAttributes.Attributes = 192;
  v20 = v10;
  FileHandle = 0;
  IoStatusBlock = 0;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v11 = NtOpenFile(&FileHandle, a4, &ObjectAttributes, &IoStatusBlock, 7u, a1 != 0 ? 33 : 96);
  if ( v11 >= 0 )
  {
    v13 = v20 == 0;
    *a3 = FileHandle;
    FileHandle = 0;
    v16 = 0;
    if ( !v13 )
      RtlSetThreadErrorMode(OldMode, 0);
    v12 = 0;
  }
  else
  {
    v12 = v11 | 0x10000000;
    v16 = v11 | 0x10000000;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_Zd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        10,
        (unsigned int)&WPP_58242705c75132cdab80b446e38b4c82_Traceguids,
        (_DWORD)a2,
        v11);
    }
    if ( FileHandle )
      NtClose(FileHandle);
    if ( v20 )
      RtlSetThreadErrorMode(OldMode, 0);
  }
  CHResultImp::~CHResultImp((CHResultImp *)v15);
  return v12;
}

```

## disassembly

```asm
0x14000b490  mov     [rsp-28h+arg_0], rbx
0x14000b495  push    rbp
0x14000b496  push    rsi
0x14000b497  push    rdi
0x14000b498  push    r12
0x14000b49a  push    r14
0x14000b49c  mov     rbp, rsp
0x14000b49f  sub     rsp, 80h
0x14000b4a6  mov     rax, gs:58h
0x14000b4af  mov     bl, cl
0x14000b4b1  mov     ecx, 8
0x14000b4b6  mov     edi, r9d
0x14000b4b9  mov     rsi, r8
0x14000b4bc  mov     r14, rdx
0x14000b4bf  mov     r10, [rax]
0x14000b4c2  lea     rax, aOpenvolumehand; "OpenVolumeHandle"
0x14000b4c9  mov     [rcx+r10], rax
0x14000b4cd  lea     rcx, [rbp+var_50]; this
0x14000b4d1  call    ??0CHResultImp@@QEAA@XZ; CHResultImp::CHResultImp(void)
0x14000b4d6  mov     qword ptr [rsi], 0
0x14000b4dd  mov     [rbp+arg_C], 0
0x14000b4e1  call    cs:__imp_RtlGetThreadErrorMode
0x14000b4e7  or      eax, 10h
0x14000b4ea  lea     rdx, [rbp+OldMode]; OldMode
0x14000b4ee  mov     ecx, eax; NewMode
0x14000b4f0  call    cs:__imp_RtlSetThreadErrorMode
0x14000b4f6  movzx   ecx, [rbp+arg_C]
0x14000b4fa  lea     r9, [rbp+IoStatusBlock]; IoStatusBlock
0x14000b4fe  test    eax, eax
0x14000b500  mov     qword ptr [rbp+ObjectAttributes.Length], 30h ; '0'
0x14000b508  xorps   xmm0, xmm0
0x14000b50b  mov     [rbp+ObjectAttributes.RootDirectory], 0
0x14000b513  mov     r12d, 1
0x14000b519  mov     [rbp+ObjectAttributes.ObjectName], r14
0x14000b51d  cmovns  ecx, r12d
0x14000b521  mov     qword ptr [rbp+ObjectAttributes.Attributes], 0C0h
0x14000b529  mov     [rbp+arg_C], cl
0x14000b52c  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x14000b530  neg     bl
0x14000b532  mov     [rbp+FileHandle], 0
0x14000b53a  mov     edx, edi; DesiredAccess
0x14000b53c  lea     rcx, [rbp+FileHandle]; FileHandle
0x14000b540  sbb     eax, eax
0x14000b542  and     eax, 0FFFFFFC1h
0x14000b545  add     eax, 60h ; '`'
0x14000b548  mov     [rsp+80h+OpenOptions], eax; OpenOptions
0x14000b54c  mov     [rsp+80h+ShareAccess], 7; ShareAccess
0x14000b554  movups  xmmword ptr [rbp+IoStatusBlock], xmm0
0x14000b558  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x14000b55d  call    cs:__imp_NtOpenFile
0x14000b563  test    eax, eax
0x14000b565  jns     short loc_14000B5CD
0x14000b567  mov     ebx, eax
0x14000b569  bts     ebx, 1Ch
0x14000b56d  mov     [rbp+var_48], ebx
0x14000b570  mov     rcx, cs:WPP_GLOBAL_Control
0x14000b577  lea     rdx, WPP_GLOBAL_Control
0x14000b57e  cmp     rcx, rdx
0x14000b581  jz      short loc_14000B5AB
0x14000b583  test    [rcx+1Ch], r12b
0x14000b587  jz      short loc_14000B5AB
0x14000b589  cmp     byte ptr [rcx+19h], 2
0x14000b58d  jb      short loc_14000B5AB
0x14000b58f  mov     rcx, [rcx+10h]
0x14000b593  lea     edx, [r12+9]
0x14000b598  mov     r9, r14
0x14000b59b  mov     [rsp+80h+ShareAccess], eax
0x14000b59f  lea     r8, WPP_58242705c75132cdab80b446e38b4c82_Traceguids
0x14000b5a6  call    WPP_SF_Zd
0x14000b5ab  mov     rcx, [rbp+FileHandle]; Handle
0x14000b5af  test    rcx, rcx
0x14000b5b2  jz      short loc_14000B5BA
0x14000b5b4  call    cs:__imp_NtClose
0x14000b5ba  cmp     [rbp+arg_C], 0
0x14000b5be  jz      short loc_14000B5F6
0x14000b5c0  mov     ecx, [rbp+OldMode]; NewMode
0x14000b5c3  xor     edx, edx; OldMode
0x14000b5c5  call    cs:__imp_RtlSetThreadErrorMode
0x14000b5cb  jmp     short loc_14000B5F6
0x14000b5cd  cmp     [rbp+arg_C], 0
0x14000b5d1  mov     rax, [rbp+FileHandle]
0x14000b5d5  mov     [rsi], rax
0x14000b5d8  mov     [rbp+FileHandle], 0
0x14000b5e0  mov     [rbp+var_48], 0
0x14000b5e7  jz      short loc_14000B5F4
0x14000b5e9  mov     ecx, [rbp+OldMode]; NewMode
0x14000b5ec  xor     edx, edx; OldMode
0x14000b5ee  call    cs:__imp_RtlSetThreadErrorMode
0x14000b5f4  xor     ebx, ebx
0x14000b5f6  lea     rcx, [rbp+var_50]; this
0x14000b5fa  call    ??1CHResultImp@@QEAA@XZ; CHResultImp::~CHResultImp(void)
0x14000b5ff  mov     eax, ebx
0x14000b601  mov     rbx, [rsp+80h+arg_0]
0x14000b609  add     rsp, 80h
0x14000b610  pop     r14
0x14000b612  pop     r12
0x14000b614  pop     rdi
0x14000b615  pop     rsi
0x14000b616  pop     rbp
0x14000b617  retn
```
