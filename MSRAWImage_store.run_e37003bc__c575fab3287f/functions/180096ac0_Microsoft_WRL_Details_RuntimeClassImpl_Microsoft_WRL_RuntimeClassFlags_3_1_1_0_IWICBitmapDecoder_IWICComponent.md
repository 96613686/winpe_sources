# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,IWICBitmapDecoder,IWICComponentInternal,Windows::Media::IMediaExtension,Microsoft::WRL::CloakedIid<IMFTransform>,Microsoft::WRL::CloakedIid<IMFTelemetryComponent>,Microsoft::WRL::FtmBase>::Release(void)

- ea: `0x180096ac0`
- end: `0x180096b39`
- name: `?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00$00$0A@UIWICBitmapDecoder@@UIWICComponentInternal@@UIMediaExtension@Media@Windows@@U?$CloakedIid@UIMFTransform@@@23@U?$CloakedIid@UIMFTelemetryComponent@@@23@VFtmBase@23@@Details@WRL@Microsoft@@UEAAKXZ`
- size: `121`
- prototype: ``
- caller_count: `9`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18009583c`
- `0x180096b40`
- `0x180096b50`
- `0x180096b60`
- `0x180096b70`
- `0x180096b80`
- `0x180096b90`
- `0x180096ba0`
- `0x180096c10`

## callees

- `0x180096ac0`
- `0x180096d20`
- `0x1800b4010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,IWICBitmapDecoder,IWICComponentInternal,Windows::Media::IMediaExtension,Microsoft::WRL::CloakedIid<IMFTransform>,Microsoft::WRL::CloakedIid<IMFTelemetryComponent>,Microsoft::WRL::FtmBase>::Release(
        __int64 a1,
        volatile int *a2)
{
  signed __int64 v2; // rax
  __int64 v3; // r10
  unsigned int v4; // ebx
  signed __int64 v5; // rtt

  v2 = *(_QWORD *)(a1 + 96);
  v3 = a1;
  while ( v2 >= 0 )
  {
    if ( (_DWORD)v2 == 0x7FFFFFFF )
      return 2147483646;
    v4 = v2 - 1;
    v5 = v2;
    v2 = _InterlockedCompareExchange64((volatile signed __int64 *)(a1 + 96), v2 - 1, v2);
    if ( v5 == v2 )
      goto LABEL_8;
  }
  v4 = Microsoft::WRL::Details::SafeUnknownDecrementReference((Microsoft::WRL::Details *)(2 * v2 + 16), a2);
LABEL_8:
  if ( !v4 )
  {
    if ( v3 )
      (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v3 + 48LL))(v3, 1);
    if ( Microsoft::WRL::Details::ModuleBase::module_ )
      (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                           + 16LL))(Microsoft::WRL::Details::ModuleBase::module_);
  }
  return v4;
}

```

## disassembly

```asm
0x180096ac0  push    rbx
0x180096ac2  sub     rsp, 20h
0x180096ac6  mov     rax, [rcx+60h]
0x180096aca  mov     r10, rcx
0x180096acd  test    rax, rax
0x180096ad0  js      short loc_180096AEE
0x180096ad2  cmp     eax, 7FFFFFFFh
0x180096ad7  jz      short loc_180096AE7
0x180096ad9  lea     rbx, [rax-1]
0x180096add  lock cmpxchg [rcx+60h], rbx
0x180096ae3  jnz     short loc_180096ACD
0x180096ae5  jmp     short loc_180096AFD
0x180096ae7  mov     ebx, 7FFFFFFEh
0x180096aec  jmp     short loc_180096B30
0x180096aee  lea     rcx, ds:10h[rax*2]; this
0x180096af6  call    ?SafeUnknownDecrementReference@Details@WRL@Microsoft@@YAKAECJ@Z; Microsoft::WRL::Details::SafeUnknownDecrementReference(long volatile &)
0x180096afb  mov     ebx, eax
0x180096afd  test    ebx, ebx
0x180096aff  jnz     short loc_180096B30
0x180096b01  test    r10, r10
0x180096b04  jz      short loc_180096B18
0x180096b06  mov     rcx, [r10]
0x180096b09  lea     edx, [rbx+1]
0x180096b0c  mov     rax, [rcx+30h]
0x180096b10  mov     rcx, r10
0x180096b13  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180096b18  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x180096b1f  test    rcx, rcx
0x180096b22  jz      short loc_180096B30
0x180096b24  mov     rax, [rcx]
0x180096b27  mov     rax, [rax+10h]
0x180096b2b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180096b30  mov     eax, ebx
0x180096b32  add     rsp, 20h
0x180096b36  pop     rbx
0x180096b37  retn
```
