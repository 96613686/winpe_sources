# FltpEnlistTxVolContextInTransaction

- ea: `0x18004fa38`
- end: `0x18004fbe9`
- name: `FltpEnlistTxVolContextInTransaction`
- size: `433`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x18004fca0`

## callees

- `0x180009f20`
- `0x18004fa38`

## import_xrefs

- `ntoskrnl!ObfDereferenceObject` at `0x18004fb93`
- `ntoskrnl!ObfDereferenceObject` at `0x18004fb93`
- `ntoskrnl!ZwClose` at `0x18004fb7e`
- `ntoskrnl!ZwClose` at `0x18004fb7e`
- `ntoskrnl!TmReadOnlyEnlistment` at `0x18004fb6e`
- `ntoskrnl!TmReadOnlyEnlistment` at `0x18004fb6e`
- `ntoskrnl!TmCreateEnlistment` at `0x18004fac1`
- `ntoskrnl!TmCreateEnlistment` at `0x18004fac1`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x18004fb15`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x18004fb15`

## pseudocode

```c
__int64 __fastcall FltpEnlistTxVolContextInTransaction(struct _KTRANSACTION *a1, __int64 a2)
{
  unsigned int v3; // edi
  void *v4; // rax
  OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+50h] [rbp-30h] BYREF
  void *EnlistmentHandle; // [rsp+98h] [rbp+18h] BYREF
  PVOID Object; // [rsp+A8h] [rbp+28h] BYREF

  *(_QWORD *)(a2 + 24) = -3;
  *(_DWORD *)(a2 + 32) = 1073741832;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.ObjectName = 0;
  Object = 0;
  EnlistmentHandle = 0;
  *(_QWORD *)&ObjectAttributes.Length = 48;
  *(_QWORD *)&ObjectAttributes.Attributes = 512;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v3 = TmCreateEnlistment(
         &EnlistmentHandle,
         0,
         0xF001Fu,
         &ObjectAttributes,
         (PRKRESOURCEMANAGER)qword_18003ED10,
         a1,
         0,
         0xCu,
         (PVOID)a2);
  if ( (int)FltpDbgStatus(v3, "minkernel\\fs\\filtermgr\\filter\\txvolcontextsup.c", 1801, 0) >= 0 )
  {
    v3 = ObReferenceObjectByHandle(EnlistmentHandle, 0, 0, 0, &Object, 0);
    if ( (int)FltpDbgStatus(v3, "minkernel\\fs\\filtermgr\\filter\\txvolcontextsup.c", 1837, 0) >= 0 )
    {
      *(_QWORD *)(a2 + 24) = Object;
      *(_QWORD *)(a2 + 16) = EnlistmentHandle;
      _InterlockedIncrement((volatile signed __int32 *)(a2 + 144));
      v4 = 0;
      EnlistmentHandle = 0;
    }
    else
    {
      v4 = EnlistmentHandle;
    }
    Object = 0;
    if ( !v4 )
      goto LABEL_10;
    TmReadOnlyEnlistment(0, 0);
    ZwClose(EnlistmentHandle);
  }
  else
  {
    EnlistmentHandle = 0;
  }
  if ( Object )
    ObfDereferenceObject(Object);
LABEL_10:
  if ( (int)FltpDbgStatus(v3, "minkernel\\fs\\filtermgr\\filter\\txvolcontextsup.c", 1909, 0) < 0
    && v3 != -1071906789
    && *(_QWORD *)(a2 + 24) == -3 )
  {
    *(_QWORD *)(a2 + 24) = -1;
  }
  return v3;
}

```

## disassembly

```asm
0x18004fa38  mov     r11, rsp
0x18004fa3b  mov     [r11+8], rbx
0x18004fa3f  mov     [r11+18h], rdi
0x18004fa43  push    rbp
0x18004fa44  mov     rbp, rsp
0x18004fa47  sub     rsp, 80h
0x18004fa4e  mov     [r11-48h], rdx
0x18004fa52  lea     r9, [rbp+ObjectAttributes]; ObjectAttributes
0x18004fa56  xor     eax, eax
0x18004fa58  mov     [rsp+80h+NotificationMask], 0Ch; NotificationMask
0x18004fa60  mov     [rsp+80h+CreateOptions], eax; CreateOptions
0x18004fa64  mov     rbx, rdx
0x18004fa67  mov     qword ptr [rdx+18h], 0FFFFFFFFFFFFFFFDh
0x18004fa6f  xorps   xmm0, xmm0
0x18004fa72  mov     dword ptr [rdx+20h], 40000008h
0x18004fa79  mov     r8d, 0F001Fh; DesiredAccess
0x18004fa7f  mov     [r11-60h], rcx
0x18004fa83  xor     edx, edx; PreviousMode
0x18004fa85  mov     [rbp+ObjectAttributes.RootDirectory], rax
0x18004fa89  lea     rcx, [rbp+EnlistmentHandle]; EnlistmentHandle
0x18004fa8d  mov     [rbp+ObjectAttributes.ObjectName], rax
0x18004fa91  mov     rax, cs:qword_18003ED10
0x18004fa98  mov     [r11-68h], rax
0x18004fa9c  mov     [rbp+arg_18], 0
0x18004faa4  mov     [rbp+EnlistmentHandle], 0
0x18004faac  mov     qword ptr [rbp+ObjectAttributes.Length], 30h ; '0'
0x18004fab4  mov     qword ptr [rbp+ObjectAttributes.Attributes], 200h
0x18004fabc  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x18004fac1  call    cs:__imp_TmCreateEnlistment
0x18004fac8  nop     dword ptr [rax+rax+00h]
0x18004facd  mov     r8d, 709h
0x18004fad3  lea     rdx, aMinkernelFsFil_26; "minkernel\\fs\\filtermgr\\filter\\txvol"...
0x18004fada  mov     ecx, eax
0x18004fadc  xor     r9d, r9d
0x18004fadf  mov     edi, eax
0x18004fae1  call    FltpDbgStatus
0x18004fae6  test    eax, eax
0x18004fae8  jns     short loc_18004FAF7
0x18004faea  mov     [rbp+EnlistmentHandle], 0
0x18004faf2  jmp     loc_18004FB8A
0x18004faf7  mov     rcx, [rbp+EnlistmentHandle]; Handle
0x18004fafb  lea     rax, [rbp+arg_18]
0x18004faff  mov     [rsp+80h+HandleInformation], 0; HandleInformation
0x18004fb08  xor     r9d, r9d; AccessMode
0x18004fb0b  xor     r8d, r8d; ObjectType
0x18004fb0e  mov     [rsp+80h+Object], rax; Object
0x18004fb13  xor     edx, edx; DesiredAccess
0x18004fb15  call    cs:__imp_ObReferenceObjectByHandle
0x18004fb1c  nop     dword ptr [rax+rax+00h]
0x18004fb21  mov     r8d, 72Dh
0x18004fb27  lea     rdx, aMinkernelFsFil_26; "minkernel\\fs\\filtermgr\\filter\\txvol"...
0x18004fb2e  mov     ecx, eax
0x18004fb30  xor     r9d, r9d
0x18004fb33  mov     edi, eax
0x18004fb35  call    FltpDbgStatus
0x18004fb3a  test    eax, eax
0x18004fb3c  jns     short loc_18004FB44
0x18004fb3e  mov     rax, [rbp+EnlistmentHandle]
0x18004fb42  jmp     short loc_18004FB61
0x18004fb44  mov     rax, [rbp+arg_18]
0x18004fb48  mov     [rbx+18h], rax
0x18004fb4c  mov     rax, [rbp+EnlistmentHandle]
0x18004fb50  mov     [rbx+10h], rax
0x18004fb54  lock inc dword ptr [rbx+90h]
0x18004fb5b  xor     eax, eax
0x18004fb5d  mov     [rbp+EnlistmentHandle], rax
0x18004fb61  xor     ecx, ecx; Enlistment
0x18004fb63  mov     [rbp+arg_18], rcx
0x18004fb67  test    rax, rax
0x18004fb6a  jz      short loc_18004FB9F
0x18004fb6c  xor     edx, edx; TmVirtualClock
0x18004fb6e  call    cs:__imp_TmReadOnlyEnlistment
0x18004fb75  nop     dword ptr [rax+rax+00h]
0x18004fb7a  mov     rcx, [rbp+EnlistmentHandle]; Handle
0x18004fb7e  call    cs:__imp_ZwClose
0x18004fb85  nop     dword ptr [rax+rax+00h]
0x18004fb8a  mov     rcx, [rbp+arg_18]; Object
0x18004fb8e  test    rcx, rcx
0x18004fb91  jz      short loc_18004FB9F
0x18004fb93  call    cs:__imp_ObfDereferenceObject
0x18004fb9a  nop     dword ptr [rax+rax+00h]
0x18004fb9f  mov     r8d, 775h
0x18004fba5  lea     rdx, aMinkernelFsFil_26; "minkernel\\fs\\filtermgr\\filter\\txvol"...
0x18004fbac  xor     r9d, r9d
0x18004fbaf  mov     ecx, edi
0x18004fbb1  call    FltpDbgStatus
0x18004fbb6  test    eax, eax
0x18004fbb8  jns     short loc_18004FBD1
0x18004fbba  cmp     edi, 0C01C001Bh
0x18004fbc0  jz      short loc_18004FBD1
0x18004fbc2  cmp     qword ptr [rbx+18h], 0FFFFFFFFFFFFFFFDh
0x18004fbc7  jnz     short loc_18004FBD1
0x18004fbc9  mov     qword ptr [rbx+18h], 0FFFFFFFFFFFFFFFFh
0x18004fbd1  lea     r11, [rsp+80h+var_s0]
0x18004fbd9  mov     eax, edi
0x18004fbdb  mov     rbx, [r11+10h]
0x18004fbdf  mov     rdi, [r11+20h]
0x18004fbe3  mov     rsp, r11
0x18004fbe6  pop     rbp
0x18004fbe7  retn
```
