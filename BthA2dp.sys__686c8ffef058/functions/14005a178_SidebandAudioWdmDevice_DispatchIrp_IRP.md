# SidebandAudioWdmDevice::DispatchIrp(_IRP *)

- ea: `0x14005a178`
- end: `0x14005a31d`
- name: `?DispatchIrp@SidebandAudioWdmDevice@@IEAA?AV?$optional@J@utl@@PEAU_IRP@@@Z`
- size: `421`
- prototype: `__int64 __fastcall(SidebandAudioWdmDevice *this, __int64, IRP *)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x140015290`

## callees

- `0x140005030`
- `0x14000f950`
- `0x14001f830`
- `0x1400208e8`
- `0x140036814`
- `0x14005a178`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x14005a2f9`
- `ntoskrnl!IofCompleteRequest` at `0x14005a2f9`
- `ntoskrnl!RtlCompareUnicodeString` at `0x14005a1ae`
- `ntoskrnl!RtlCompareUnicodeString` at `0x14005a1ae`

## pseudocode

```c
__int64 __fastcall SidebandAudioWdmDevice::DispatchIrp(SidebandAudioWdmDevice *this, __int64 a2, IRP *a3)
{
  struct _IO_STACK_LOCATION *CurrentStackLocation; // r14
  bool v7; // zf
  int v8; // ebx
  char v9; // al
  int v10; // edx
  int v11; // r8d
  _BYTE v13[56]; // [rsp+70h] [rbp-38h] BYREF

  CurrentStackLocation = a3->Tail.Overlay.CurrentStackLocation;
  if ( CurrentStackLocation->MajorFunction )
  {
    wil::acquire_kspin_lock(v13, (char *)this + 16);
    if ( !SidebandAudioWdmDevice::IsKnownFileObject(this, CurrentStackLocation->FileObject) )
    {
      *(_QWORD *)a2 = 0;
      wil::details::unique_storage<wil::details::resource_policy<unsigned __int64 *,void (wil::details::kspin_lock_saved_irql const &),&public: static void wil::details::kspin_lock_saved_irql::Release(wil::details::kspin_lock_saved_irql const &),wistd::integral_constant<unsigned __int64,2>,wil::details::kspin_lock_saved_irql,unsigned __int64 *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64 *,void (wil::details::kspin_lock_saved_irql const &),&public: static void wil::details::kspin_lock_saved_irql::Release(wil::details::kspin_lock_saved_irql const &),wistd::integral_constant<unsigned __int64,2>,wil::details::kspin_lock_saved_irql,unsigned __int64 *,0,std::nullptr_t>>(v13);
      return a2;
    }
    if ( CurrentStackLocation->MajorFunction == 2 )
      goto LABEL_8;
    v9 = *((_BYTE *)this + 80);
    if ( CurrentStackLocation->MajorFunction != 14 )
    {
      v8 = v9 != 0 ? -1073741808 : -1073741436;
      goto LABEL_14;
    }
    v7 = v9 == 0;
  }
  else
  {
    if ( RtlCompareUnicodeString(
           &CurrentStackLocation->FileObject->FileName,
           (PCUNICODE_STRING)((char *)this + 440),
           1u) )
    {
      *(_QWORD *)a2 = 0;
      return a2;
    }
    wil::acquire_kspin_lock(v13, (char *)this + 16);
    v7 = *((_BYTE *)this + 80) == 0;
  }
  if ( v7 )
  {
    v8 = -1073741436;
    goto LABEL_14;
  }
LABEL_8:
  v8 = SidebandAudioWdmDevice::EnqueueIrp(this, a3);
LABEL_14:
  wil::details::unique_storage<wil::details::resource_policy<unsigned __int64 *,void (wil::details::kspin_lock_saved_irql const &),&public: static void wil::details::kspin_lock_saved_irql::Release(wil::details::kspin_lock_saved_irql const &),wistd::integral_constant<unsigned __int64,2>,wil::details::kspin_lock_saved_irql,unsigned __int64 *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64 *,void (wil::details::kspin_lock_saved_irql const &),&public: static void wil::details::kspin_lock_saved_irql::Release(wil::details::kspin_lock_saved_irql const &),wistd::integral_constant<unsigned __int64,2>,wil::details::kspin_lock_saved_irql,unsigned __int64 *,0,std::nullptr_t>>(v13);
  if ( v8 < 0 )
  {
    LOBYTE(v10) = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
               && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
               && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u;
    if ( (_BYTE)v10 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v11) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      WPP_RECORDER_AND_TRACE_SF_cLdqq(
        WPP_GLOBAL_Control->AttachedDevice,
        v10,
        v11,
        WPP_GLOBAL_Control->DeviceExtension,
        2,
        1,
        24,
        (__int64)WPP_6f6ca3ff72523c797fc054add42d8828_Traceguids,
        CurrentStackLocation->MajorFunction,
        CurrentStackLocation->Parameters.Read.ByteOffset.LowPart,
        v8,
        (char)CurrentStackLocation->FileObject,
        (char)this);
    }
    a3->IoStatus.Information = 0;
    a3->IoStatus.Status = v8;
    IofCompleteRequest(a3, 0);
  }
  *(_DWORD *)a2 = v8;
  *(_BYTE *)(a2 + 4) = 1;
  return a2;
}

```

## disassembly

```asm
0x14005a178  push    rbx
0x14005a17a  push    rbp
0x14005a17b  push    rsi
0x14005a17c  push    rdi
0x14005a17d  push    r14
0x14005a17f  sub     rsp, 80h
0x14005a186  mov     r14, [r8+0B8h]
0x14005a18d  mov     rbp, r8
0x14005a190  mov     rdi, rdx
0x14005a193  mov     rsi, rcx
0x14005a196  cmp     byte ptr [r14], 0
0x14005a19a  jnz     short loc_14005A1DC
0x14005a19c  lea     rdx, [rcx+1B8h]; String2
0x14005a1a3  mov     r8b, 1; CaseInSensitive
0x14005a1a6  mov     rcx, [r14+30h]
0x14005a1aa  add     rcx, 58h ; 'X'; String1
0x14005a1ae  call    cs:__imp_RtlCompareUnicodeString
0x14005a1b5  nop     dword ptr [rax+rax+00h]
0x14005a1ba  test    eax, eax
0x14005a1bc  jz      short loc_14005A1C8
0x14005a1be  xor     eax, eax
0x14005a1c0  mov     [rdi], rax
0x14005a1c3  jmp     loc_14005A30B
0x14005a1c8  lea     rdx, [rsi+10h]
0x14005a1cc  lea     rcx, [rsp+0A8h+var_38]
0x14005a1d1  call    ?acquire_kspin_lock@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_K$$A6AXAEBUkspin_lock_saved_irql@details@wil@@@Z$1?Release@123@SAX0@ZU?$integral_constant@_K$01@wistd@@U123@PEA_K$0A@$$T@details@wil@@@details@wil@@@1@PEA_K@Z; wil::acquire_kspin_lock(unsigned __int64 *)
0x14005a1d6  cmp     byte ptr [rsi+50h], 0
0x14005a1da  jmp     short loc_14005A22F
0x14005a1dc  lea     rdx, [rcx+10h]
0x14005a1e0  lea     rcx, [rsp+0A8h+var_38]
0x14005a1e5  call    ?acquire_kspin_lock@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_K$$A6AXAEBUkspin_lock_saved_irql@details@wil@@@Z$1?Release@123@SAX0@ZU?$integral_constant@_K$01@wistd@@U123@PEA_K$0A@$$T@details@wil@@@details@wil@@@1@PEA_K@Z; wil::acquire_kspin_lock(unsigned __int64 *)
0x14005a1ea  mov     rdx, [r14+30h]; struct _FILE_OBJECT *
0x14005a1ee  mov     rcx, rsi; this
0x14005a1f1  call    ?IsKnownFileObject@SidebandAudioWdmDevice@@AEAA_NQEAU_FILE_OBJECT@@@Z; SidebandAudioWdmDevice::IsKnownFileObject(_FILE_OBJECT * const)
0x14005a1f6  test    al, al
0x14005a1f8  jnz     short loc_14005A20E
0x14005a1fa  xor     eax, eax
0x14005a1fc  lea     rcx, [rsp+0A8h+var_38]
0x14005a201  mov     [rdi], rax
0x14005a204  call    ??1?$unique_storage@U?$resource_policy@PEA_K$$A6AXAEBUkspin_lock_saved_irql@details@wil@@@Z$1?Release@123@SAX0@ZU?$integral_constant@_K$01@wistd@@U123@PEA_K$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64 *,void (wil::details::kspin_lock_saved_irql const &),&wil::details::kspin_lock_saved_irql::Release(wil::details::kspin_lock_saved_irql const &),wistd::integral_constant<unsigned __int64,2>,wil::details::kspin_lock_saved_irql,unsigned __int64 *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64 *,void (wil::details::kspin_lock_saved_irql const &),&wil::details::kspin_lock_saved_irql::Release(wil::details::kspin_lock_saved_irql const &),wistd::integral_constant<unsigned __int64,2>,wil::details::kspin_lock_saved_irql,unsigned __int64 *,0,std::nullptr_t>>(void)
0x14005a209  jmp     loc_14005A30B
0x14005a20e  mov     cl, [r14]
0x14005a211  cmp     cl, 2
0x14005a214  jnz     short loc_14005A225
0x14005a216  mov     rdx, rbp; struct _IRP *
0x14005a219  mov     rcx, rsi; this
0x14005a21c  call    ?EnqueueIrp@SidebandAudioWdmDevice@@IEAAJPEAU_IRP@@@Z; SidebandAudioWdmDevice::EnqueueIrp(_IRP *)
0x14005a221  mov     ebx, eax
0x14005a223  jmp     short loc_14005A248
0x14005a225  mov     al, [rsi+50h]
0x14005a228  cmp     cl, 0Eh
0x14005a22b  jnz     short loc_14005A238
0x14005a22d  test    al, al
0x14005a22f  jnz     short loc_14005A216
0x14005a231  mov     ebx, 0C0000184h
0x14005a236  jmp     short loc_14005A248
0x14005a238  neg     al
0x14005a23a  mov     ebx, 0C0000184h
0x14005a23f  sbb     eax, eax
0x14005a241  and     eax, 0FFFFFE8Ch
0x14005a246  add     ebx, eax
0x14005a248  lea     rcx, [rsp+0A8h+var_38]
0x14005a24d  call    ??1?$unique_storage@U?$resource_policy@PEA_K$$A6AXAEBUkspin_lock_saved_irql@details@wil@@@Z$1?Release@123@SAX0@ZU?$integral_constant@_K$01@wistd@@U123@PEA_K$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64 *,void (wil::details::kspin_lock_saved_irql const &),&wil::details::kspin_lock_saved_irql::Release(wil::details::kspin_lock_saved_irql const &),wistd::integral_constant<unsigned __int64,2>,wil::details::kspin_lock_saved_irql,unsigned __int64 *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64 *,void (wil::details::kspin_lock_saved_irql const &),&wil::details::kspin_lock_saved_irql::Release(wil::details::kspin_lock_saved_irql const &),wistd::integral_constant<unsigned __int64,2>,wil::details::kspin_lock_saved_irql,unsigned __int64 *,0,std::nullptr_t>>(void)
0x14005a252  test    ebx, ebx
0x14005a254  jns     loc_14005A305
0x14005a25a  mov     rcx, cs:WPP_GLOBAL_Control
0x14005a261  lea     rax, WPP_GLOBAL_Control
0x14005a268  cmp     rcx, rax
0x14005a26b  jz      short loc_14005A27E
0x14005a26d  mov     eax, [rcx+2Ch]
0x14005a270  test    al, 1
0x14005a272  jz      short loc_14005A27E
0x14005a274  cmp     byte ptr [rcx+29h], 2
0x14005a278  jb      short loc_14005A27E
0x14005a27a  mov     dl, 1
0x14005a27c  jmp     short loc_14005A280
0x14005a27e  xor     dl, dl
0x14005a280  lea     rax, WPP_RECORDER_INITIALIZED
0x14005a287  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14005a28e  setnz   r8b
0x14005a292  test    dl, dl
0x14005a294  jnz     short loc_14005A29B
0x14005a296  test    r8b, r8b
0x14005a299  jz      short loc_14005A2E9
0x14005a29b  mov     rax, [r14+30h]
0x14005a29f  mov     r9, [rcx+40h]
0x14005a2a3  mov     rcx, [rcx+18h]
0x14005a2a7  mov     [rsp+0A8h+var_48], rsi
0x14005a2ac  mov     [rsp+0A8h+var_50], rax
0x14005a2b1  mov     eax, [r14+18h]
0x14005a2b5  mov     [rsp+0A8h+var_58], ebx
0x14005a2b9  mov     [rsp+0A8h+var_60], eax
0x14005a2bd  mov     al, [r14]
0x14005a2c0  mov     [rsp+0A8h+var_68], al
0x14005a2c4  lea     rax, WPP_6f6ca3ff72523c797fc054add42d8828_Traceguids
0x14005a2cb  mov     [rsp+0A8h+var_70], rax
0x14005a2d0  mov     [rsp+0A8h+var_78], 18h
0x14005a2d7  mov     [rsp+0A8h+var_80], 1
0x14005a2df  mov     [rsp+0A8h+var_88], 2
0x14005a2e4  call    WPP_RECORDER_AND_TRACE_SF_cLdqq
0x14005a2e9  xor     edx, edx; PriorityBoost
0x14005a2eb  mov     qword ptr [rbp+38h], 0
0x14005a2f3  mov     rcx, rbp; Irp
0x14005a2f6  mov     [rbp+30h], ebx
0x14005a2f9  call    cs:__imp_IofCompleteRequest
0x14005a300  nop     dword ptr [rax+rax+00h]
0x14005a305  mov     [rdi], ebx
0x14005a307  mov     byte ptr [rdi+4], 1
0x14005a30b  mov     rax, rdi
0x14005a30e  add     rsp, 80h
0x14005a315  pop     r14
0x14005a317  pop     rdi
0x14005a318  pop     rsi
0x14005a319  pop     rbp
0x14005a31a  pop     rbx
0x14005a31b  retn
```
