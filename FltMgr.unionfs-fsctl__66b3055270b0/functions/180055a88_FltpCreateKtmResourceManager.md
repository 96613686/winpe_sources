# FltpCreateKtmResourceManager

- ea: `0x180055a88`
- end: `0x180055d1f`
- name: `FltpCreateKtmResourceManager`
- size: `663`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x18004c810`
- `0x18004fca0`

## callees

- `0x180009f20`
- `0x1800247a0`
- `0x180055a88`

## import_xrefs

- `ntoskrnl!ObfDereferenceObject` at `0x180055c90`
- `ntoskrnl!ObfDereferenceObject` at `0x180055d0e`
- `ntoskrnl!ObfDereferenceObject` at `0x180055c90`
- `ntoskrnl!ObfDereferenceObject` at `0x180055d0e`
- `ntoskrnl!ZwClose` at `0x180055b6c`
- `ntoskrnl!ZwClose` at `0x180055c5e`
- `ntoskrnl!ZwClose` at `0x180055c80`
- `ntoskrnl!ZwClose` at `0x180055cfe`
- `ntoskrnl!ZwClose` at `0x180055b6c`
- `ntoskrnl!ZwClose` at `0x180055c5e`
- `ntoskrnl!ZwClose` at `0x180055c80`
- `ntoskrnl!ZwClose` at `0x180055cfe`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x180055c35`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x180055c35`
- `ntoskrnl!ZwCreateTransactionManager` at `0x180055b2b`
- `ntoskrnl!ZwCreateTransactionManager` at `0x180055b2b`
- `ntoskrnl!ExUuidCreate` at `0x180055b85`
- `ntoskrnl!ExUuidCreate` at `0x180055b85`
- `ntoskrnl!ZwCreateResourceManager` at `0x180055bf2`
- `ntoskrnl!ZwCreateResourceManager` at `0x180055bf2`
- `ntoskrnl!TmEnableCallbacks` at `0x180055ccf`
- `ntoskrnl!TmEnableCallbacks` at `0x180055ccf`

## pseudocode

```c
__int64 __fastcall FltpCreateKtmResourceManager(
        void **a1,
        PKRESOURCEMANAGER *a2,
        NTSTATUS (__stdcall *a3)(PKENLISTMENT EnlistmentObject, PVOID RMContext, PVOID TransactionContext, ULONG TransactionNotification, PLARGE_INTEGER TmVirtualClock, ULONG ArgumentLength, PVOID Argument),
        void *a4)
{
  unsigned int v8; // edi
  void *v10; // rcx
  void *ResourceManagerHandle; // [rsp+40h] [rbp-49h] BYREF
  PVOID Object; // [rsp+48h] [rbp-41h] BYREF
  void *TmHandle; // [rsp+50h] [rbp-39h] BYREF
  OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+58h] [rbp-31h] BYREF
  UUID Uuid; // [rsp+88h] [rbp-1h] BYREF

  Object = 0;
  memset(&ObjectAttributes, 0, 44);
  ResourceManagerHandle = 0;
  TmHandle = 0;
  Uuid = 0;
  if ( !::TmHandle )
  {
    ObjectAttributes.Length = 48;
    ObjectAttributes.RootDirectory = 0;
    ObjectAttributes.Attributes = 512;
    ObjectAttributes.ObjectName = 0;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    v8 = ZwCreateTransactionManager(&TmHandle, 0xF003Fu, &ObjectAttributes, 0, 1u, 0);
    if ( (int)FltpDbgStatus(v8, "minkernel\\fs\\filtermgr\\filter\\transsup.c", 139, 0) < 0 )
      return v8;
    if ( _InterlockedCompareExchange64((volatile signed __int64 *)&::TmHandle, (signed __int64)TmHandle, 0) )
      ZwClose(TmHandle);
  }
  if ( !*a1 )
  {
    v8 = ExUuidCreate(&Uuid);
    if ( (int)FltpDbgStatus(v8, "minkernel\\fs\\filtermgr\\filter\\transsup.c", 173, 0) < 0 )
      return v8;
    ObjectAttributes.Length = 48;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    ObjectAttributes.RootDirectory = 0;
    ObjectAttributes.Attributes = 512;
    ObjectAttributes.ObjectName = 0;
    v8 = ZwCreateResourceManager(&ResourceManagerHandle, 0x1F007Fu, ::TmHandle, &Uuid, &ObjectAttributes, 1u, 0);
    if ( (int)FltpDbgStatus(v8, "minkernel\\fs\\filtermgr\\filter\\transsup.c", 196, 0) < 0 )
      return v8;
    v8 = ObReferenceObjectByHandle(ResourceManagerHandle, 0, 0, 0, &Object, 0);
    if ( (int)FltpDbgStatus(v8, "minkernel\\fs\\filtermgr\\filter\\transsup.c", 212, 0) < 0 )
    {
      ZwClose(ResourceManagerHandle);
      return v8;
    }
    if ( _InterlockedCompareExchange64((volatile signed __int64 *)a2, (signed __int64)Object, 0) )
    {
      ZwClose(ResourceManagerHandle);
      ObfDereferenceObject(Object);
    }
    else
    {
      *a1 = ResourceManagerHandle;
      v8 = TmEnableCallbacks(*a2, a3, a4);
      if ( (int)FltpDbgStatus(v8, "minkernel\\fs\\filtermgr\\filter\\transsup.c", 247, 0) < 0 )
      {
        v10 = ResourceManagerHandle;
        *a2 = 0;
        *a1 = 0;
        ZwClose(v10);
        ObfDereferenceObject(Object);
        return v8;
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180055a88  push    rbp
0x180055a8a  push    rbx
0x180055a8b  push    rsi
0x180055a8c  push    rdi
0x180055a8d  push    r12
0x180055a8f  push    r13
0x180055a91  push    r14
0x180055a93  push    r15
0x180055a95  lea     rbp, [rsp-1Fh]
0x180055a9a  sub     rsp, 0A8h
0x180055aa1  mov     rax, cs:__security_cookie
0x180055aa8  xor     rax, rsp
0x180055aab  mov     [rbp+57h+var_48], rax
0x180055aaf  xorps   xmm0, xmm0
0x180055ab2  lea     r13, aMinkernelFsFil_6; "minkernel\\fs\\filtermgr\\filter\\trans"...
0x180055ab9  xor     r12d, r12d
0x180055abc  xor     eax, eax
0x180055abe  cmp     cs:TmHandle, r12
0x180055ac5  mov     r15, r9
0x180055ac8  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x180055acc  mov     r14, r8
0x180055acf  mov     rbx, rdx
0x180055ad2  movups  xmmword ptr [rbp+57h+ObjectAttributes+1Ch], xmm0
0x180055ad6  mov     rsi, rcx
0x180055ad9  mov     [rbp+57h+Object], r12
0x180055add  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x180055ae1  mov     [rbp+57h+ResourceManagerHandle], r12
0x180055ae5  mov     [rbp+57h+TmHandle], r12
0x180055ae9  movups  xmmword ptr [rbp+57h+Uuid.Data1], xmm0
0x180055aed  jnz     loc_180055B78
0x180055af3  mov     [rsp+0E0h+CommitStrength], r12d; CommitStrength
0x180055af8  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x180055afc  xor     r9d, r9d; LogFileName
0x180055aff  mov     [rsp+0E0h+CreateOptions], 1; CreateOptions
0x180055b07  mov     edx, 0F003Fh; DesiredAccess
0x180055b0c  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x180055b13  lea     rcx, [rbp+57h+TmHandle]; TmHandle
0x180055b17  mov     [rbp+57h+ObjectAttributes.RootDirectory], r12
0x180055b1b  mov     [rbp+57h+ObjectAttributes.Attributes], 200h
0x180055b22  mov     [rbp+57h+ObjectAttributes.ObjectName], r12
0x180055b26  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x180055b2b  call    cs:__imp_ZwCreateTransactionManager
0x180055b32  nop     dword ptr [rax+rax+00h]
0x180055b37  mov     r8d, 8Bh
0x180055b3d  xor     r9d, r9d
0x180055b40  mov     ecx, eax
0x180055b42  mov     rdx, r13
0x180055b45  mov     edi, eax
0x180055b47  call    FltpDbgStatus
0x180055b4c  test    eax, eax
0x180055b4e  jns     short loc_180055B57
0x180055b50  mov     eax, edi
0x180055b52  jmp     loc_180055C9E
0x180055b57  mov     rcx, [rbp+57h+TmHandle]
0x180055b5b  xor     eax, eax
0x180055b5d  lock cmpxchg cs:TmHandle, rcx
0x180055b66  jz      short loc_180055B78
0x180055b68  mov     rcx, [rbp+57h+TmHandle]; Handle
0x180055b6c  call    cs:__imp_ZwClose
0x180055b73  nop     dword ptr [rax+rax+00h]
0x180055b78  cmp     [rsi], r12
0x180055b7b  jnz     loc_180055C9C
0x180055b81  lea     rcx, [rbp+57h+Uuid]; Uuid
0x180055b85  call    cs:__imp_ExUuidCreate
0x180055b8c  nop     dword ptr [rax+rax+00h]
0x180055b91  mov     r8d, 0ADh
0x180055b97  xor     r9d, r9d
0x180055b9a  mov     ecx, eax
0x180055b9c  mov     rdx, r13
0x180055b9f  mov     edi, eax
0x180055ba1  call    FltpDbgStatus
0x180055ba6  test    eax, eax
0x180055ba8  js      short loc_180055B50
0x180055baa  mov     r8, cs:TmHandle; TmHandle
0x180055bb1  lea     rax, [rbp+57h+ObjectAttributes]
0x180055bb5  xorps   xmm0, xmm0
0x180055bb8  mov     [rsp+0E0h+Description], r12; Description
0x180055bbd  mov     [rsp+0E0h+CommitStrength], 1; CreateOptions
0x180055bc5  lea     r9, [rbp+57h+Uuid]; ResourceManagerGuid
0x180055bc9  mov     edx, 1F007Fh; DesiredAccess
0x180055bce  mov     qword ptr [rsp+0E0h+CreateOptions], rax; ObjectAttributes
0x180055bd3  lea     rcx, [rbp+57h+ResourceManagerHandle]; ResourceManagerHandle
0x180055bd7  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x180055bde  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x180055be3  mov     [rbp+57h+ObjectAttributes.RootDirectory], r12
0x180055be7  mov     [rbp+57h+ObjectAttributes.Attributes], 200h
0x180055bee  mov     [rbp+57h+ObjectAttributes.ObjectName], r12
0x180055bf2  call    cs:__imp_ZwCreateResourceManager
0x180055bf9  nop     dword ptr [rax+rax+00h]
0x180055bfe  mov     r8d, 0C4h
0x180055c04  xor     r9d, r9d
0x180055c07  mov     ecx, eax
0x180055c09  mov     rdx, r13
0x180055c0c  mov     edi, eax
0x180055c0e  call    FltpDbgStatus
0x180055c13  test    eax, eax
0x180055c15  js      loc_180055B50
0x180055c1b  mov     rcx, [rbp+57h+ResourceManagerHandle]; Handle
0x180055c1f  lea     rax, [rbp+57h+Object]
0x180055c23  mov     qword ptr [rsp+0E0h+CommitStrength], r12; HandleInformation
0x180055c28  xor     r9d, r9d; AccessMode
0x180055c2b  xor     r8d, r8d; ObjectType
0x180055c2e  mov     qword ptr [rsp+0E0h+CreateOptions], rax; Object
0x180055c33  xor     edx, edx; DesiredAccess
0x180055c35  call    cs:__imp_ObReferenceObjectByHandle
0x180055c3c  nop     dword ptr [rax+rax+00h]
0x180055c41  mov     r8d, 0D4h
0x180055c47  xor     r9d, r9d
0x180055c4a  mov     ecx, eax
0x180055c4c  mov     rdx, r13
0x180055c4f  mov     edi, eax
0x180055c51  call    FltpDbgStatus
0x180055c56  test    eax, eax
0x180055c58  jns     short loc_180055C6F
0x180055c5a  mov     rcx, [rbp+57h+ResourceManagerHandle]; Handle
0x180055c5e  call    cs:__imp_ZwClose
0x180055c65  nop     dword ptr [rax+rax+00h]
0x180055c6a  jmp     loc_180055B50
0x180055c6f  mov     rcx, [rbp+57h+Object]
0x180055c73  xor     eax, eax
0x180055c75  lock cmpxchg [rbx], rcx
0x180055c7a  jz      short loc_180055CBF
0x180055c7c  mov     rcx, [rbp+57h+ResourceManagerHandle]; Handle
0x180055c80  call    cs:__imp_ZwClose
0x180055c87  nop     dword ptr [rax+rax+00h]
0x180055c8c  mov     rcx, [rbp+57h+Object]; Object
0x180055c90  call    cs:__imp_ObfDereferenceObject
0x180055c97  nop     dword ptr [rax+rax+00h]
0x180055c9c  xor     eax, eax
0x180055c9e  mov     rcx, [rbp+57h+var_48]
0x180055ca2  xor     rcx, rsp; StackCookie
0x180055ca5  call    __security_check_cookie
0x180055caa  add     rsp, 0A8h
0x180055cb1  pop     r15
0x180055cb3  pop     r14
0x180055cb5  pop     r13
0x180055cb7  pop     r12
0x180055cb9  pop     rdi
0x180055cba  pop     rsi
0x180055cbb  pop     rbx
0x180055cbc  pop     rbp
0x180055cbd  retn
0x180055cbf  mov     rax, [rbp+57h+ResourceManagerHandle]
0x180055cc3  mov     r8, r15; RMKey
0x180055cc6  mov     [rsi], rax
0x180055cc9  mov     rdx, r14; CallbackRoutine
0x180055ccc  mov     rcx, [rbx]; ResourceManager
0x180055ccf  call    cs:__imp_TmEnableCallbacks
0x180055cd6  nop     dword ptr [rax+rax+00h]
0x180055cdb  mov     r8d, 0F7h
0x180055ce1  xor     r9d, r9d
0x180055ce4  mov     ecx, eax
0x180055ce6  mov     rdx, r13
0x180055ce9  mov     edi, eax
0x180055ceb  call    FltpDbgStatus
0x180055cf0  test    eax, eax
0x180055cf2  jns     short loc_180055C9C
0x180055cf4  mov     rcx, [rbp+57h+ResourceManagerHandle]; Handle
0x180055cf8  mov     [rbx], r12
0x180055cfb  mov     [rsi], r12
0x180055cfe  call    cs:__imp_ZwClose
0x180055d05  nop     dword ptr [rax+rax+00h]
0x180055d0a  mov     rcx, [rbp+57h+Object]; Object
0x180055d0e  call    cs:__imp_ObfDereferenceObject
0x180055d15  nop     dword ptr [rax+rax+00h]
0x180055d1a  jmp     loc_180055B50
```
