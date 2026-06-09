# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,IWICBitmapDecoder,IWICComponentInternal,Windows::Media::IMediaExtension,Microsoft::WRL::CloakedIid<IMFTransform>,Microsoft::WRL::CloakedIid<IMFTelemetryComponent>,Microsoft::WRL::FtmBase>::GetWeakReference(IWeakReference * *)

- ea: `0x1800966a0`
- end: `0x18009676a`
- name: `?GetWeakReference@?$RuntimeClassImpl@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00$00$0A@UIWICBitmapDecoder@@UIWICComponentInternal@@UIMediaExtension@Media@Windows@@U?$CloakedIid@UIMFTransform@@@23@U?$CloakedIid@UIMFTelemetryComponent@@@23@VFtmBase@23@@Details@WRL@Microsoft@@UEAAJPEAPEAUIWeakReference@@@Z`
- size: `202`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1800956c8`
- `0x180095d80`
- `0x1800966a0`
- `0x180096a60`
- `0x180096d4c`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,IWICBitmapDecoder,IWICComponentInternal,Windows::Media::IMediaExtension,Microsoft::WRL::CloakedIid<IMFTransform>,Microsoft::WRL::CloakedIid<IMFTelemetryComponent>,Microsoft::WRL::FtmBase>::GetWeakReference(
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

  v2 = *(_QWORD *)(a1 + 80);
  *(_QWORD *)a2 = 0;
  if ( v2 >= 0 )
  {
    v12 = a1 - 16;
    v6 = Microsoft::WRL::Details::Make<Microsoft::WRL::Details::WeakReferenceImpl,IUnknown * &>(&v11, &v12);
    v7 = *v6;
    *v6 = 0;
    if ( v11 )
    {
      v11 = 0;
      Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IWeakReference>::Release();
    }
    if ( !v7 )
      return 2147942414LL;
    while ( 1 )
    {
      *(_DWORD *)(v7 + 16) = v2;
      v10 = _InterlockedCompareExchange64((volatile signed __int64 *)(a1 + 80), (v7 >> 1) | 0x8000000000000000uLL, v2);
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
0x1800966a0  mov     [rsp+arg_10], rbx
0x1800966a5  push    rbp
0x1800966a6  push    rsi
0x1800966a7  push    rdi
0x1800966a8  sub     rsp, 20h
0x1800966ac  mov     rbx, [rcx+50h]
0x1800966b0  mov     rsi, rdx
0x1800966b3  mov     qword ptr [rdx], 0
0x1800966ba  mov     rbp, rcx
0x1800966bd  test    rbx, rbx
0x1800966c0  jns     short loc_1800966D6
0x1800966c2  add     rbx, rbx
0x1800966c5  lea     rcx, [rbx+0Ch]; this
0x1800966c9  call    ?SafeUnknownIncrementReference@Details@WRL@Microsoft@@YAKAECJ@Z; Microsoft::WRL::Details::SafeUnknownIncrementReference(long volatile &)
0x1800966ce  mov     [rsi], rbx
0x1800966d1  jmp     loc_18009675A
0x1800966d6  lea     rax, [rcx-10h]
0x1800966da  lea     rcx, [rsp+38h+arg_0]
0x1800966df  mov     [rsp+38h+arg_8], rax
0x1800966e4  lea     rdx, [rsp+38h+arg_8]
0x1800966e9  call    ??$Make@VWeakReferenceImpl@Details@WRL@Microsoft@@AEAPEAUIUnknown@@@Details@WRL@Microsoft@@YA?AV?$ComPtr@VWeakReferenceImpl@Details@WRL@Microsoft@@@12@AEAPEAUIUnknown@@@Z; Microsoft::WRL::Details::Make<Microsoft::WRL::Details::WeakReferenceImpl,IUnknown * &>(IUnknown * &)
0x1800966ee  mov     rdi, [rax]
0x1800966f1  mov     qword ptr [rax], 0
0x1800966f8  mov     rcx, [rsp+38h+arg_0]
0x1800966fd  test    rcx, rcx
0x180096700  jz      short loc_180096710
0x180096702  mov     [rsp+38h+arg_0], 0
0x18009670b  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIWeakReference@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IWeakReference>::Release(void)
0x180096710  test    rdi, rdi
0x180096713  jnz     short loc_18009671C
0x180096715  mov     eax, 8007000Eh
0x18009671a  jmp     short loc_18009675C
0x18009671c  mov     rcx, rdi
0x18009671f  mov     rax, 8000000000000000h
0x180096729  sar     rcx, 1
0x18009672c  or      rcx, rax
0x18009672f  mov     [rdi+10h], ebx
0x180096732  mov     rax, rbx
0x180096735  lock cmpxchg [rbp+50h], rcx
0x18009673b  mov     rbx, rax
0x18009673e  jz      short loc_180096757
0x180096740  test    rax, rax
0x180096743  jns     short loc_18009672F
0x180096745  mov     edx, 1; unsigned int
0x18009674a  mov     rcx, rdi; this
0x18009674d  call    ??_EWeakReferenceImpl@Details@WRL@Microsoft@@UEAAPEAXI@Z; Microsoft::WRL::Details::WeakReferenceImpl::`vector deleting destructor'(uint)
0x180096752  jmp     loc_1800966C2
0x180096757  mov     [rsi], rdi
0x18009675a  xor     eax, eax
0x18009675c  mov     rbx, [rsp+38h+arg_10]
0x180096761  add     rsp, 20h
0x180096765  pop     rdi
0x180096766  pop     rsi
0x180096767  pop     rbp
0x180096768  retn
```
