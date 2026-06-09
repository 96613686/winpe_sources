# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<19>,1,1,0,Windows::Storage::Streams::IBuffer,Microsoft::WRL::CloakedIid<Windows::Storage::Streams::IBufferByteAccess>,Microsoft::WRL::CloakedIid<IMarshal>,Microsoft::WRL::FtmBase>::GetWeakReference(IWeakReference * *)

- ea: `0x140009570`
- end: `0x140009639`
- name: `?GetWeakReference@?$RuntimeClassImpl@U?$RuntimeClassFlags@$0BD@@WRL@Microsoft@@$00$00$0A@UIBuffer@Streams@Storage@Windows@@U?$CloakedIid@UIBufferByteAccess@Streams@Storage@Windows@@@23@U?$CloakedIid@UIMarshal@@@23@VFtmBase@23@@Details@WRL@Microsoft@@UEAAJPEAPEAUIWeakReference@@@Z`
- size: `201`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x140005d90`
- `0x140008150`
- `0x1400086f8`
- `0x140008a60`
- `0x140009570`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<19>,1,1,0,Windows::Storage::Streams::IBuffer,Microsoft::WRL::CloakedIid<Windows::Storage::Streams::IBufferByteAccess>,Microsoft::WRL::CloakedIid<IMarshal>,Microsoft::WRL::FtmBase>::GetWeakReference(
        __int64 a1,
        volatile int *a2)
{
  signed __int64 v2; // rbx
  __int64 v5; // rbx
  __int64 *v6; // rax
  __int64 v7; // rdi
  bool v9; // zf
  __int64 v10; // rax
  __int64 v11; // [rsp+40h] [rbp+8h] BYREF
  __int64 v12; // [rsp+48h] [rbp+10h] BYREF

  v2 = *(_QWORD *)(a1 + 64);
  *(_QWORD *)a2 = 0;
  if ( v2 >= 0 )
  {
    v12 = a1 - 8;
    v6 = Microsoft::WRL::Details::Make<Microsoft::WRL::Details::WeakReferenceImpl,IUnknown * &>(&v11, &v12);
    v7 = *v6;
    *v6 = 0;
    if ( v11 )
    {
      v11 = 0;
      Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Foundation::ITypedEventHandler<Windows::UI::Core::CoreDispatcher *,Windows::UI::Core::AcceleratorKeyEventArgs *>>::Release();
    }
    if ( !v7 )
      return 2147942414LL;
    while ( 1 )
    {
      *(_DWORD *)(v7 + 16) = v2;
      v10 = _InterlockedCompareExchange64((volatile signed __int64 *)(a1 + 64), (v7 >> 1) | 0x8000000000000000uLL, v2);
      v9 = v2 == v10;
      v2 = v10;
      if ( v9 )
        break;
      if ( v10 < 0 )
      {
        Microsoft::WRL::Details::WeakReferenceImpl::`vector deleting destructor'(
          (Microsoft::WRL::Details::WeakReferenceImpl *)v7,
          1u);
        goto LABEL_2;
      }
    }
    *(_QWORD *)a2 = v7;
  }
  else
  {
LABEL_2:
    v5 = 2 * v2;
    Microsoft::WRL::Details::SafeUnknownIncrementReference((Microsoft::WRL::Details *)(v5 + 12), a2);
    *(_QWORD *)a2 = v5;
  }
  return 0;
}

```

## disassembly

```asm
0x140009570  mov     [rsp+arg_10], rbx
0x140009575  push    rbp
0x140009576  push    rsi
0x140009577  push    rdi
0x140009578  sub     rsp, 20h
0x14000957c  mov     rbx, [rcx+40h]
0x140009580  mov     rsi, rdx
0x140009583  mov     qword ptr [rdx], 0
0x14000958a  mov     rbp, rcx
0x14000958d  test    rbx, rbx
0x140009590  jns     short loc_1400095A6
0x140009592  add     rbx, rbx
0x140009595  lea     rcx, [rbx+0Ch]; this
0x140009599  call    ?SafeUnknownIncrementReference@Details@WRL@Microsoft@@YAKAECJ@Z; Microsoft::WRL::Details::SafeUnknownIncrementReference(long volatile &)
0x14000959e  mov     [rsi], rbx
0x1400095a1  jmp     loc_14000962A
0x1400095a6  lea     rax, [rcx-8]
0x1400095aa  lea     rcx, [rsp+38h+arg_0]
0x1400095af  mov     [rsp+38h+arg_8], rax
0x1400095b4  lea     rdx, [rsp+38h+arg_8]
0x1400095b9  call    ??$Make@VWeakReferenceImpl@Details@WRL@Microsoft@@AEAPEAUIUnknown@@@Details@WRL@Microsoft@@YA?AV?$ComPtr@VWeakReferenceImpl@Details@WRL@Microsoft@@@12@AEAPEAUIUnknown@@@Z; Microsoft::WRL::Details::Make<Microsoft::WRL::Details::WeakReferenceImpl,IUnknown * &>(IUnknown * &)
0x1400095be  mov     rdi, [rax]
0x1400095c1  mov     qword ptr [rax], 0
0x1400095c8  mov     rcx, [rsp+38h+arg_0]
0x1400095cd  test    rcx, rcx
0x1400095d0  jz      short loc_1400095E0
0x1400095d2  mov     [rsp+38h+arg_0], 0
0x1400095db  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@U?$ITypedEventHandler@PEAVCoreDispatcher@Core@UI@Windows@@PEAVAcceleratorKeyEventArgs@234@@Foundation@Windows@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Foundation::ITypedEventHandler<Windows::UI::Core::CoreDispatcher *,Windows::UI::Core::AcceleratorKeyEventArgs *>>::Release(void)
0x1400095e0  test    rdi, rdi
0x1400095e3  jnz     short loc_1400095EC
0x1400095e5  mov     eax, 8007000Eh
0x1400095ea  jmp     short loc_14000962C
0x1400095ec  mov     rcx, rdi
0x1400095ef  mov     rax, 8000000000000000h
0x1400095f9  sar     rcx, 1
0x1400095fc  or      rcx, rax
0x1400095ff  mov     [rdi+10h], ebx
0x140009602  mov     rax, rbx
0x140009605  lock cmpxchg [rbp+40h], rcx
0x14000960b  mov     rbx, rax
0x14000960e  jz      short loc_140009627
0x140009610  test    rax, rax
0x140009613  jns     short loc_1400095FF
0x140009615  mov     edx, 1; unsigned int
0x14000961a  mov     rcx, rdi; this
0x14000961d  call    ??_EWeakReferenceImpl@Details@WRL@Microsoft@@UEAAPEAXI@Z; Microsoft::WRL::Details::WeakReferenceImpl::`vector deleting destructor'(uint)
0x140009622  jmp     loc_140009592
0x140009627  mov     [rsi], rdi
0x14000962a  xor     eax, eax
0x14000962c  mov     rbx, [rsp+38h+arg_10]
0x140009631  add     rsp, 20h
0x140009635  pop     rdi
0x140009636  pop     rsi
0x140009637  pop     rbp
0x140009638  retn
```
