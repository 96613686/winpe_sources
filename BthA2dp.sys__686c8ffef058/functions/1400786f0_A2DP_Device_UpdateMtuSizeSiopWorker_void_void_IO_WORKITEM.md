# A2DP_Device::UpdateMtuSizeSiopWorker(void *,void *,_IO_WORKITEM *)

- ea: `0x1400786f0`
- end: `0x140078860`
- name: `?UpdateMtuSizeSiopWorker@A2DP_Device@@_C2PAGE@@AXPEAX0PEAU_IO_WORKITEM@@@Z`
- size: `368`
- prototype: `IO_WORKITEM_ROUTINE_EX`
- caller_count: `0`
- callee_count: `9`
- tags: `authz_impersonation, loader_planting, installer_update`

## callees

- `0x140006380`
- `0x140006410`
- `0x140006b70`
- `0x14000f570`
- `0x14001bbc4`
- `0x14005c870`
- `0x140078404`
- `0x1400786f0`
- `0x140078db4`

## import_xrefs

- `ntoskrnl!IoFreeWorkItem` at `0x14007883b`
- `ntoskrnl!IoFreeWorkItem` at `0x14007883b`

## string_xrefs

- `0x140078829`: `UpdateMtuSizeSiopWorker`

## pseudocode

```c
void __fastcall A2DP_Device::UpdateMtuSizeSiopWorker(PVOID IoObject, A2DP_Device *Context, PIO_WORKITEM IoWorkItem)
{
  char v3; // bl
  struct _IO_WORKITEM *v4; // rbp
  A2DP_Device *v5; // rdi
  __int64 v6; // rcx
  __int64 CurrentSelectedCodec; // rax
  bool v8; // si
  int v9; // eax
  unsigned __int16 v10; // bx
  __int64 v11; // rcx
  utl::_RefCountBase *v12[2]; // [rsp+40h] [rbp-48h] BYREF
  A2dpSidebandAudioWdmEndpoint *v13; // [rsp+50h] [rbp-38h] BYREF
  utl::_RefCountBase *v14; // [rsp+58h] [rbp-30h]

  v3 = 0;
  v4 = IoWorkItem;
  v5 = Context;
  LOBYTE(Context) = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                 && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
                 && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u;
  if ( (_BYTE)Context || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(IoWorkItem) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    WPP_RECORDER_AND_TRACE_SF_(
      WPP_GLOBAL_Control->AttachedDevice,
      (_DWORD)Context,
      (_DWORD)IoWorkItem,
      WPP_GLOBAL_Control->DeviceExtension,
      4,
      5,
      130,
      (__int64)WPP_4800887547dd3d4e33fad0eec8a4812f_Traceguids);
  }
  *(_OWORD *)v12 = 0;
  v8 = 0;
  if ( v5 )
  {
    v6 = *((_QWORD *)v5 + 1);
    if ( v6 )
    {
      CurrentSelectedCodec = A2dpRole::GetCurrentSelectedCodec(v6, &v13);
      v3 = 1;
      if ( *(_QWORD *)utl::shared_ptr<A2dpAudioCodec>::operator=(v12, CurrentSelectedCodec) )
        v8 = 1;
    }
  }
  if ( (v3 & 1) != 0 && v14 )
    utl::_RefCountBase::_DecStrong(v14);
  if ( v8 )
  {
    v9 = (*(__int64 (__fastcall **)(utl::_RefCountBase *))(*(_QWORD *)v12[0] + 120LL))(v12[0]);
    v10 = v9;
    if ( (unsigned int)(v9 - 1) <= 0xFFFE )
    {
      v11 = *((_QWORD *)v5 + 434);
      if ( v11 )
      {
        SidebandAudioWdmDevice::GetEndpointAtIndex(v11, &v13);
        if ( v13 )
          A2dpSidebandAudioWdmEndpoint::UpdateMtuSizeSiop(v13, v10);
        if ( v14 )
          utl::_RefCountBase::_DecStrong(v14);
      }
    }
  }
  A2DP_Device::Release(v5, 13, "UpdateMtuSizeSiopWorker");
  IoFreeWorkItem(v4);
  if ( v12[1] )
    utl::_RefCountBase::_DecStrong(v12[1]);
}

```

## disassembly

```asm
0x1400786f0  push    rbx
0x1400786f2  push    rbp
0x1400786f3  push    rsi
0x1400786f4  push    rdi
0x1400786f5  sub     rsp, 68h
0x1400786f9  xor     ebx, ebx
0x1400786fb  mov     rbp, r8
0x1400786fe  mov     [rsp+88h+arg_8], ebx
0x140078705  mov     rdi, rdx
0x140078708  mov     rcx, cs:WPP_GLOBAL_Control
0x14007870f  lea     rax, WPP_GLOBAL_Control
0x140078716  cmp     rcx, rax
0x140078719  jz      short loc_14007872C
0x14007871b  mov     eax, [rcx+2Ch]
0x14007871e  test    al, 10h
0x140078720  jz      short loc_14007872C
0x140078722  cmp     byte ptr [rcx+29h], 4
0x140078726  jb      short loc_14007872C
0x140078728  mov     dl, 1
0x14007872a  jmp     short loc_14007872E
0x14007872c  xor     dl, dl
0x14007872e  lea     rax, WPP_RECORDER_INITIALIZED
0x140078735  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14007873c  setnz   r8b
0x140078740  test    dl, dl
0x140078742  jnz     short loc_140078749
0x140078744  test    r8b, r8b
0x140078747  jz      short loc_140078776
0x140078749  mov     r9, [rcx+40h]
0x14007874d  lea     rax, WPP_4800887547dd3d4e33fad0eec8a4812f_Traceguids
0x140078754  mov     rcx, [rcx+18h]
0x140078758  mov     [rsp+88h+var_50], rax
0x14007875d  mov     [rsp+88h+var_58], 82h
0x140078764  mov     [rsp+88h+var_60], 5
0x14007876c  mov     [rsp+88h+var_68], 4
0x140078771  call    WPP_RECORDER_AND_TRACE_SF_
0x140078776  xorps   xmm0, xmm0
0x140078779  movdqu  xmmword ptr [rsp+88h+var_48], xmm0
0x14007877f  test    rdi, rdi
0x140078782  jz      short loc_1400787B3
0x140078784  mov     rcx, [rdi+8]
0x140078788  test    rcx, rcx
0x14007878b  jz      short loc_1400787B3
0x14007878d  lea     rdx, [rsp+88h+var_38]
0x140078792  call    ?GetCurrentSelectedCodec@A2dpRole@@QEBA?AV?$shared_ptr@VA2dpAudioCodec@@@utl@@XZ; A2dpRole::GetCurrentSelectedCodec(void)
0x140078797  mov     rdx, rax
0x14007879a  lea     rcx, [rsp+88h+var_48]
0x14007879f  call    ??4?$shared_ptr@VA2dpAudioCodec@@@utl@@QEAAAEAV01@$$QEAV01@@Z; utl::shared_ptr<A2dpAudioCodec>::operator=(utl::shared_ptr<A2dpAudioCodec> &&)
0x1400787a4  cmp     [rax], rbx
0x1400787a7  mov     ebx, 1
0x1400787ac  jz      short loc_1400787B3
0x1400787ae  mov     sil, bl
0x1400787b1  jmp     short loc_1400787B6
0x1400787b3  xor     sil, sil
0x1400787b6  test    bl, 1
0x1400787b9  jz      short loc_1400787CA
0x1400787bb  mov     rcx, [rsp+88h+var_30]; this
0x1400787c0  test    rcx, rcx
0x1400787c3  jz      short loc_1400787CA
0x1400787c5  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x1400787ca  test    sil, sil
0x1400787cd  jz      short loc_140078824
0x1400787cf  mov     rcx, [rsp+88h+var_48]
0x1400787d4  mov     rax, [rcx]
0x1400787d7  mov     rax, [rax+78h]
0x1400787db  call    _guard_dispatch_icall
0x1400787e0  mov     ebx, eax
0x1400787e2  lea     ecx, [rax-1]
0x1400787e5  cmp     ecx, 0FFFEh
0x1400787eb  ja      short loc_140078824
0x1400787ed  mov     rcx, [rdi+0D90h]
0x1400787f4  test    rcx, rcx
0x1400787f7  jz      short loc_140078824
0x1400787f9  lea     rdx, [rsp+88h+var_38]
0x1400787fe  call    ?GetEndpointAtIndex@SidebandAudioWdmDevice@@IEBA?AV?$shared_ptr@VSidebandAudioWdmEndpoint@@@utl@@G@Z; SidebandAudioWdmDevice::GetEndpointAtIndex(ushort)
0x140078803  mov     rcx, [rsp+88h+var_38]; this
0x140078808  test    rcx, rcx
0x14007880b  jz      short loc_140078815
0x14007880d  movzx   edx, bx; unsigned __int16
0x140078810  call    ?UpdateMtuSizeSiop@A2dpSidebandAudioWdmEndpoint@@QEAAXG@Z; A2dpSidebandAudioWdmEndpoint::UpdateMtuSizeSiop(ushort)
0x140078815  mov     rcx, [rsp+88h+var_30]; this
0x14007881a  test    rcx, rcx
0x14007881d  jz      short loc_140078824
0x14007881f  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x140078824  mov     edx, 0Dh; __int16
0x140078829  lea     r8, aUpdatemtusizes; "UpdateMtuSizeSiopWorker"
0x140078830  mov     rcx, rdi; this
0x140078833  call    ?Release@A2DP_Device@@QEAAXFPEBD@Z; A2DP_Device::Release(short,char const *)
0x140078838  mov     rcx, rbp; IoWorkItem
0x14007883b  call    cs:__imp_IoFreeWorkItem
0x140078842  nop     dword ptr [rax+rax+00h]
0x140078847  mov     rcx, [rsp+88h+var_48+8]; this
0x14007884c  test    rcx, rcx
0x14007884f  jz      short loc_140078856
0x140078851  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x140078856  add     rsp, 68h
0x14007885a  pop     rdi
0x14007885b  pop     rsi
0x14007885c  pop     rbp
0x14007885d  pop     rbx
0x14007885e  retn
```
