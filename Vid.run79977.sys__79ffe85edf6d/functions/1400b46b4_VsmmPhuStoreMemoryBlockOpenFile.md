# VsmmPhuStoreMemoryBlockOpenFile

- ea: `0x1400b46b4`
- end: `0x1400b4a9a`
- name: `VsmmPhuStoreMemoryBlockOpenFile`
- size: `998`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x1400a21d4`

## callees

- `0x1400029c0`
- `0x140006b68`
- `0x14000a010`
- `0x140021c60`
- `0x14002f724`
- `0x1400305c0`
- `0x140076678`
- `0x1400b46b4`
- `0x1400e1528`

## import_xrefs

- `ntoskrnl!ObReferenceObjectByHandle` at `0x1400b48c1`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x1400b48c1`
- `ntoskrnl!ObfDereferenceObject` at `0x1400b4959`
- `ntoskrnl!ObfDereferenceObject` at `0x1400b4959`
- `ntoskrnl!ObOpenObjectByPointer` at `0x1400b491f`
- `ntoskrnl!ObOpenObjectByPointer` at `0x1400b491f`
- `ntoskrnl!IoFileObjectType` at `0x1400b4893`
- `ntoskrnl!IoFileObjectType` at `0x1400b4906`

## string_xrefs

- `0x1400b471f`: `VsmmPhuStoreMemoryBlockOpenFile`
- `0x1400b475c`: `VsmmPhuStoreMemoryBlockOpenFile`
- `0x1400b4796`: `VsmmPhuStoreMemoryBlockOpenFile`
- `0x1400b47fb`: `VsmmPhuStoreMemoryBlockOpenFile`
- `0x1400b48e8`: `VsmmPhuStoreMemoryBlockOpenFile`
- `0x1400b4941`: `VsmmPhuStoreMemoryBlockOpenFile`
- `0x1400b49a6`: `VsmmPhuStoreMemoryBlockOpenFile`

## pseudocode

```c
__int64 __fastcall VsmmPhuStoreMemoryBlockOpenFile(__int64 a1, __int64 a2, ACCESS_MASK a3, void **a4)
{
  char *v4; // r14
  __int64 v8; // rax
  __int64 v9; // r15
  int v10; // ebx
  int v11; // eax
  void **v12; // rcx
  int v13; // r8d
  void *v14; // rcx
  NTSTATUS v15; // eax
  PVOID v16; // r15
  NTSTATUS v17; // eax
  char v19; // [rsp+40h] [rbp-C0h] BYREF
  PVOID Object; // [rsp+48h] [rbp-B8h] BYREF
  PHANDLE Handle; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v22; // [rsp+58h] [rbp-A8h] BYREF
  _BYTE v23[32]; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v24[16]; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v25[16]; // [rsp+90h] [rbp-70h] BYREF
  void *p_Object; // [rsp+A0h] [rbp-60h]
  __int64 v27; // [rsp+A8h] [rbp-58h]
  void *p_Handle; // [rsp+B0h] [rbp-50h]
  __int64 v29; // [rsp+B8h] [rbp-48h]
  char *v30; // [rsp+C0h] [rbp-40h]
  __int64 v31; // [rsp+C8h] [rbp-38h]
  _DWORD *v32; // [rsp+D0h] [rbp-30h]
  __int64 v33; // [rsp+D8h] [rbp-28h]
  __int64 v34; // [rsp+E0h] [rbp-20h]
  _DWORD v35[2]; // [rsp+E8h] [rbp-18h] BYREF
  __int64 *v36; // [rsp+F0h] [rbp-10h]
  __int64 v37; // [rsp+F8h] [rbp-8h]

  v4 = 0;
  Handle = a4;
  Object = 0;
  v8 = VsmmPhuStorepObjectLookup(*(_QWORD *)(a1 + 8648), 2, a2);
  v9 = v8;
  if ( !v8 )
  {
    v10 = -1073741275;
    VidTraceErrorStatusInternal0(
      "VsmmPhuStoreMemoryBlockOpenFile",
      "onecore\\vm\\vid\\sys\\vsmm\\vsmmphustore.c",
      4206,
      3221226021LL);
LABEL_24:
    if ( (unsigned int)dword_140065110 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140065110, 256) )
    {
      tlgCreate1Sz_char(v24, "VsmmPhuStoreMemoryBlockOpenFile");
      tlgCreate1Sz_char(v25, "onecore\\vm\\vid\\sys\\vsmm\\vsmmphustore.c");
      LODWORD(Object) = 4302;
      p_Object = &Object;
      v27 = 4;
      p_Handle = &Handle;
      LODWORD(Handle) = v10;
      v30 = (char *)(a1 + 656);
      v29 = 4;
      v32 = v35;
      v34 = *(_QWORD *)(a1 + 128);
      v35[0] = *(unsigned __int16 *)(a1 + 120);
      v22 = *(_QWORD *)(a1 + 648);
      v36 = &v22;
      v31 = 16;
      v33 = 2;
      v35[1] = 0;
      v37 = 8;
      tlgWriteTransfer_EtwWriteTransfer(&dword_140065110, &unk_14004FCD3, 0, 0, 10, v23);
    }
    return (unsigned int)v10;
  }
  if ( *(_BYTE *)(v8 + 72) )
  {
    v12 = *(void ***)(v8 + 152);
  }
  else
  {
    if ( !*(_BYTE *)(a1 + 8657) )
    {
      v10 = -1073741436;
      VidTraceErrorStatusInternal0(
        "VsmmPhuStoreMemoryBlockOpenFile",
        "onecore\\vm\\vid\\sys\\vsmm\\vsmmphustore.c",
        4217,
        3221225860LL);
      goto LABEL_24;
    }
    v11 = VsmmMemoryBlockLookupByPersistId(a1, a2, 0, &Object);
    v10 = v11;
    if ( v11 < 0 )
    {
      VidTraceErrorStatusInternal0(
        "VsmmPhuStoreMemoryBlockOpenFile",
        "onecore\\vm\\vid\\sys\\vsmm\\vsmmphustore.c",
        4233,
        (unsigned int)v11);
      v4 = (char *)Object;
      goto LABEL_21;
    }
    v4 = (char *)Object;
    v12 = (void **)*((_QWORD *)Object + 105);
  }
  if ( v12 )
  {
    v14 = *v12;
    Object = 0;
    v15 = ObReferenceObjectByHandle(v14, 0, (POBJECT_TYPE)IoFileObjectType, 0, &Object, 0);
    v16 = Object;
    v10 = v15;
    if ( v15 >= 0 )
    {
      v17 = ObOpenObjectByPointer(Object, 0, 0, a3, (POBJECT_TYPE)IoFileObjectType, 1, Handle);
      v10 = v17;
      if ( v17 >= 0 )
        v10 = 0;
      else
        VidTraceErrorStatusInternal0(
          "VsmmPhuStoreMemoryBlockOpenFile",
          "onecore\\vm\\vid\\sys\\vsmm\\vsmmphustore.c",
          4285,
          (unsigned int)v17);
    }
    else
    {
      VidTraceErrorStatusInternal0(
        "VsmmPhuStoreMemoryBlockOpenFile",
        "onecore\\vm\\vid\\sys\\vsmm\\vsmmphustore.c",
        4271,
        (unsigned int)v15);
    }
    if ( v16 )
      ObfDereferenceObject(v16);
  }
  else
  {
    v10 = -1073741436;
    if ( (unsigned int)dword_140065110 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140065110, 256) )
    {
      tlgCreate1Sz_char(v24, "VsmmPhuStoreMemoryBlockOpenFile");
      tlgCreate1Sz_char(v25, "onecore\\vm\\vid\\sys\\vsmm\\vsmmphustore.c");
      LODWORD(Object) = v13;
      p_Object = &Handle;
      LODWORD(Handle) = 4249;
      p_Handle = &Object;
      v19 = *(_BYTE *)(v9 + 72);
      v27 = 4;
      v30 = &v19;
      v29 = 4;
      v31 = 1;
      tlgWriteTransfer_EtwWriteTransfer(&dword_140065110, &unk_14004FC79, 0, 0, 7, v23);
    }
  }
LABEL_21:
  if ( v4 )
    VidOpCtrlFinish(v4 + 128);
  if ( v10 < 0 )
    goto LABEL_24;
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x1400b46b4  push    rbp
0x1400b46b6  push    rbx
0x1400b46b7  push    r12
0x1400b46b9  push    r13
0x1400b46bb  push    r14
0x1400b46bd  push    r15
0x1400b46bf  lea     rbp, [rsp-18h]
0x1400b46c4  sub     rsp, 118h
0x1400b46cb  mov     rax, cs:__security_cookie
0x1400b46d2  xor     rax, rsp
0x1400b46d5  mov     [rbp+40h+var_40], rax
0x1400b46d9  xor     r14d, r14d
0x1400b46dc  mov     [rsp+140h+var_F0], r9
0x1400b46e1  mov     r12d, r8d
0x1400b46e4  mov     [rsp+140h+var_F8], r14
0x1400b46e9  mov     rbx, rdx
0x1400b46ec  mov     r13, rcx
0x1400b46ef  mov     rcx, [rcx+21C8h]
0x1400b46f6  mov     r8, rdx
0x1400b46f9  lea     edx, [r14+2]
0x1400b46fd  call    VsmmPhuStorepObjectLookup
0x1400b4702  mov     r15, rax
0x1400b4705  test    rax, rax
0x1400b4708  jnz     short loc_1400B4730
0x1400b470a  mov     ebx, 0C0000225h
0x1400b470f  mov     r9d, ebx
0x1400b4712  lea     rdx, aOnecoreVmVidSy_55; "onecore\\vm\\vid\\sys\\vsmm\\vsmmphusto"...
0x1400b4719  mov     r8d, 106Eh
0x1400b471f  lea     rcx, aVsmmphustoreme_0; "VsmmPhuStoreMemoryBlockOpenFile"
0x1400b4726  call    VidTraceErrorStatusInternal0
0x1400b472b  jmp     loc_1400B497E
0x1400b4730  cmp     [rax+48h], r14b
0x1400b4734  jnz     loc_1400B47BA
0x1400b473a  cmp     [r13+21D1h], r14b
0x1400b4741  jnz     short loc_1400B476D
0x1400b4743  mov     r8d, 0C0000184h
0x1400b4749  mov     ebx, r8d
0x1400b474c  mov     r9d, r8d
0x1400b474f  lea     rdx, aOnecoreVmVidSy_55; "onecore\\vm\\vid\\sys\\vsmm\\vsmmphusto"...
0x1400b4756  mov     r8d, 1079h
0x1400b475c  lea     rcx, aVsmmphustoreme_0; "VsmmPhuStoreMemoryBlockOpenFile"
0x1400b4763  call    VidTraceErrorStatusInternal0
0x1400b4768  jmp     loc_1400B497E
0x1400b476d  lea     r9, [rsp+140h+var_F8]
0x1400b4772  xor     r8d, r8d
0x1400b4775  mov     rdx, rbx
0x1400b4778  mov     rcx, r13
0x1400b477b  call    VsmmMemoryBlockLookupByPersistId
0x1400b4780  mov     ebx, eax
0x1400b4782  test    eax, eax
0x1400b4784  jns     short loc_1400B47AC
0x1400b4786  mov     r9d, eax
0x1400b4789  lea     rdx, aOnecoreVmVidSy_55; "onecore\\vm\\vid\\sys\\vsmm\\vsmmphusto"...
0x1400b4790  mov     r8d, 1089h
0x1400b4796  lea     rcx, aVsmmphustoreme_0; "VsmmPhuStoreMemoryBlockOpenFile"
0x1400b479d  call    VidTraceErrorStatusInternal0
0x1400b47a2  mov     r14, [rsp+140h+var_F8]
0x1400b47a7  jmp     loc_1400B4965
0x1400b47ac  mov     r14, [rsp+140h+var_F8]
0x1400b47b1  mov     rcx, [r14+348h]
0x1400b47b8  jmp     short loc_1400B47C1
0x1400b47ba  mov     rcx, [rax+98h]
0x1400b47c1  test    rcx, rcx
0x1400b47c4  jnz     loc_1400B4893
0x1400b47ca  mov     eax, cs:dword_140065110
0x1400b47d0  mov     r8d, 0C0000184h
0x1400b47d6  mov     ebx, r8d
0x1400b47d9  cmp     eax, 2
0x1400b47dc  jbe     loc_1400B4965
0x1400b47e2  mov     edx, 100h
0x1400b47e7  lea     rcx, dword_140065110
0x1400b47ee  call    _tlgKeywordOn
0x1400b47f3  test    al, al
0x1400b47f5  jz      loc_1400B4965
0x1400b47fb  lea     rdx, aVsmmphustoreme_0; "VsmmPhuStoreMemoryBlockOpenFile"
0x1400b4802  lea     rcx, [rbp+40h+var_C0]
0x1400b4806  call    _tlgCreate1Sz_char
0x1400b480b  lea     rdx, aOnecoreVmVidSy_55; "onecore\\vm\\vid\\sys\\vsmm\\vsmmphusto"...
0x1400b4812  lea     rcx, [rbp+40h+var_B0]
0x1400b4816  call    _tlgCreate1Sz_char
0x1400b481b  lea     rax, [rsp+140h+var_F0]
0x1400b4820  mov     dword ptr [rsp+140h+var_F8], r8d
0x1400b4825  mov     [rbp+40h+var_A0], rax
0x1400b4829  lea     rdx, unk_14004FC79
0x1400b4830  lea     rax, [rsp+140h+var_F8]
0x1400b4835  mov     dword ptr [rsp+140h+var_F0], 1099h
0x1400b483d  mov     [rbp+40h+var_90], rax
0x1400b4841  lea     rcx, dword_140065110
0x1400b4848  mov     al, [r15+48h]
0x1400b484c  xor     r9d, r9d
0x1400b484f  mov     [rsp+140h+var_100], al
0x1400b4853  xor     r8d, r8d
0x1400b4856  lea     rax, [rsp+140h+var_100]
0x1400b485b  mov     [rbp+40h+var_98], 4
0x1400b4863  mov     [rbp+40h+var_80], rax
0x1400b4867  lea     rax, [rsp+140h+var_E0]
0x1400b486c  mov     [rsp+140h+HandleInformation], rax
0x1400b4871  mov     dword ptr [rsp+140h+Object], 7
0x1400b4879  mov     [rbp+40h+var_88], 4
0x1400b4881  mov     [rbp+40h+var_78], 1
0x1400b4889  call    _tlgWriteTransfer_EtwWriteTransfer
0x1400b488e  jmp     loc_1400B4965
0x1400b4893  mov     r8, cs:__imp_IoFileObjectType
0x1400b489a  lea     rax, [rsp+140h+var_F8]
0x1400b489f  mov     rcx, [rcx]; Handle
0x1400b48a2  xor     r9d, r9d; AccessMode
0x1400b48a5  mov     [rsp+140h+HandleInformation], 0; HandleInformation
0x1400b48ae  xor     edx, edx; DesiredAccess
0x1400b48b0  mov     [rsp+140h+var_F8], 0
0x1400b48b9  mov     r8, [r8]; ObjectType
0x1400b48bc  mov     [rsp+140h+Object], rax; Object
0x1400b48c1  call    cs:__imp_ObReferenceObjectByHandle
0x1400b48c8  nop     dword ptr [rax+rax+00h]
0x1400b48cd  mov     r15, [rsp+140h+var_F8]
0x1400b48d2  mov     ebx, eax
0x1400b48d4  test    eax, eax
0x1400b48d6  jns     short loc_1400B48F6
0x1400b48d8  mov     r9d, eax
0x1400b48db  lea     rdx, aOnecoreVmVidSy_55; "onecore\\vm\\vid\\sys\\vsmm\\vsmmphusto"...
0x1400b48e2  mov     r8d, 10AFh
0x1400b48e8  lea     rcx, aVsmmphustoreme_0; "VsmmPhuStoreMemoryBlockOpenFile"
0x1400b48ef  call    VidTraceErrorStatusInternal0
0x1400b48f4  jmp     short loc_1400B4951
0x1400b48f6  mov     rax, [rsp+140h+var_F0]
0x1400b48fb  mov     r9d, r12d; DesiredAccess
0x1400b48fe  mov     [rsp+140h+Handle], rax; Handle
0x1400b4903  xor     r8d, r8d; PassedAccessState
0x1400b4906  mov     rax, cs:__imp_IoFileObjectType
0x1400b490d  xor     edx, edx; HandleAttributes
0x1400b490f  mov     byte ptr [rsp+140h+HandleInformation], 1; AccessMode
0x1400b4914  mov     rcx, [rax]
0x1400b4917  mov     [rsp+140h+Object], rcx; ObjectType
0x1400b491c  mov     rcx, r15; Object
0x1400b491f  call    cs:__imp_ObOpenObjectByPointer
0x1400b4926  nop     dword ptr [rax+rax+00h]
0x1400b492b  mov     ebx, eax
0x1400b492d  test    eax, eax
0x1400b492f  jns     short loc_1400B494F
0x1400b4931  mov     r9d, eax
0x1400b4934  lea     rdx, aOnecoreVmVidSy_55; "onecore\\vm\\vid\\sys\\vsmm\\vsmmphusto"...
0x1400b493b  mov     r8d, 10BDh
0x1400b4941  lea     rcx, aVsmmphustoreme_0; "VsmmPhuStoreMemoryBlockOpenFile"
0x1400b4948  call    VidTraceErrorStatusInternal0
0x1400b494d  jmp     short loc_1400B4951
0x1400b494f  xor     ebx, ebx
0x1400b4951  test    r15, r15
0x1400b4954  jz      short loc_1400B4965
0x1400b4956  mov     rcx, r15; Object
0x1400b4959  call    cs:__imp_ObfDereferenceObject
0x1400b4960  nop     dword ptr [rax+rax+00h]
0x1400b4965  test    r14, r14
0x1400b4968  jz      short loc_1400B4976
0x1400b496a  lea     rcx, [r14+80h]
0x1400b4971  call    VidOpCtrlFinish
0x1400b4976  test    ebx, ebx
0x1400b4978  jns     loc_1400B4A79
0x1400b497e  mov     eax, cs:dword_140065110
0x1400b4984  cmp     eax, 2
0x1400b4987  jbe     loc_1400B4A79
0x1400b498d  mov     edx, 100h
0x1400b4992  lea     rcx, dword_140065110
0x1400b4999  call    _tlgKeywordOn
0x1400b499e  test    al, al
0x1400b49a0  jz      loc_1400B4A79
0x1400b49a6  lea     rdx, aVsmmphustoreme_0; "VsmmPhuStoreMemoryBlockOpenFile"
0x1400b49ad  lea     rcx, [rbp+40h+var_C0]
0x1400b49b1  call    _tlgCreate1Sz_char
0x1400b49b6  lea     rdx, aOnecoreVmVidSy_55; "onecore\\vm\\vid\\sys\\vsmm\\vsmmphusto"...
0x1400b49bd  lea     rcx, [rbp+40h+var_B0]
0x1400b49c1  call    _tlgCreate1Sz_char
0x1400b49c6  lea     rax, [rsp+140h+var_F8]
0x1400b49cb  mov     dword ptr [rsp+140h+var_F8], 10CEh
0x1400b49d3  mov     [rbp+40h+var_A0], rax
0x1400b49d7  lea     rdx, unk_14004FCD3
0x1400b49de  lea     rax, [rsp+140h+var_F0]
0x1400b49e3  mov     [rbp+40h+var_98], 4
0x1400b49eb  mov     [rbp+40h+var_90], rax
0x1400b49ef  lea     rcx, dword_140065110
0x1400b49f6  lea     rax, [r13+290h]
0x1400b49fd  mov     dword ptr [rsp+140h+var_F0], ebx
0x1400b4a01  mov     [rbp+40h+var_80], rax
0x1400b4a05  xor     r9d, r9d
0x1400b4a08  lea     rax, [rbp+40h+var_58]
0x1400b4a0c  mov     [rbp+40h+var_88], 4
0x1400b4a14  mov     [rbp+40h+var_70], rax
0x1400b4a18  xor     r8d, r8d
0x1400b4a1b  mov     rax, [r13+80h]
0x1400b4a22  mov     [rbp+40h+var_60], rax
0x1400b4a26  movzx   eax, word ptr [r13+78h]
0x1400b4a2b  mov     [rbp+40h+var_58], eax
0x1400b4a2e  mov     rax, [r13+288h]
0x1400b4a35  mov     [rsp+140h+var_E8], rax
0x1400b4a3a  lea     rax, [rsp+140h+var_E8]
0x1400b4a3f  mov     [rbp+40h+var_50], rax
0x1400b4a43  lea     rax, [rsp+140h+var_E0]
0x1400b4a48  mov     [rsp+140h+HandleInformation], rax
0x1400b4a4d  mov     dword ptr [rsp+140h+Object], 0Ah
0x1400b4a55  mov     [rbp+40h+var_78], 10h
0x1400b4a5d  mov     [rbp+40h+var_68], 2
0x1400b4a65  mov     [rbp+40h+var_54], 0
0x1400b4a6c  mov     [rbp+40h+var_48], 8
0x1400b4a74  call    _tlgWriteTransfer_EtwWriteTransfer
0x1400b4a79  mov     eax, ebx
0x1400b4a7b  mov     rcx, [rbp+40h+var_40]
0x1400b4a7f  xor     rcx, rsp; StackCookie
0x1400b4a82  call    __security_check_cookie
0x1400b4a87  add     rsp, 118h
0x1400b4a8e  pop     r15
0x1400b4a90  pop     r14
0x1400b4a92  pop     r13
0x1400b4a94  pop     r12
0x1400b4a96  pop     rbx
0x1400b4a97  pop     rbp
0x1400b4a98  retn
```
