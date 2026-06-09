# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<19>,1,1,0,Windows::Storage::Streams::IBuffer,Microsoft::WRL::CloakedIid<Windows::Storage::Streams::IBufferByteAccess>,Microsoft::WRL::CloakedIid<IMarshal>,Microsoft::WRL::FtmBase>::Release(void)

- ea: `0x14000b570`
- end: `0x14000b5e8`
- name: `?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$0BD@@WRL@Microsoft@@$00$00$0A@UIBuffer@Streams@Storage@Windows@@U?$CloakedIid@UIBufferByteAccess@Streams@Storage@Windows@@@23@U?$CloakedIid@UIMarshal@@@23@VFtmBase@23@@Details@WRL@Microsoft@@UEAAKXZ`
- size: `120`
- prototype: ``
- caller_count: `5`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x14000b520`
- `0x14000b5f0`
- `0x14000b600`
- `0x14000b610`
- `0x14000b620`

## callees

- `0x140005d68`
- `0x14000b570`
- `0x140014010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<19>,1,1,0,Windows::Storage::Streams::IBuffer,Microsoft::WRL::CloakedIid<Windows::Storage::Streams::IBufferByteAccess>,Microsoft::WRL::CloakedIid<IMarshal>,Microsoft::WRL::FtmBase>::Release(
        __int64 a1,
        volatile int *a2)
{
  signed __int64 v2; // rax
  __int64 v3; // r10
  unsigned int v4; // ebx
  signed __int64 v5; // rtt

  v2 = *(_QWORD *)(a1 + 72);
  v3 = a1;
  while ( v2 >= 0 )
  {
    if ( (_DWORD)v2 == 0x7FFFFFFF )
      return 2147483646;
    v4 = v2 - 1;
    v5 = v2;
    v2 = _InterlockedCompareExchange64((volatile signed __int64 *)(a1 + 72), v2 - 1, v2);
    if ( v5 == v2 )
      goto LABEL_8;
  }
  v4 = Microsoft::WRL::Details::SafeUnknownDecrementReference((Microsoft::WRL::Details *)(2 * v2 + 16), a2);
LABEL_8:
  if ( !v4 )
  {
    if ( v3 )
      (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v3 + 72LL))(v3, 1);
    if ( Microsoft::WRL::Details::ModuleBase::module_ )
      (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                           + 16LL))(Microsoft::WRL::Details::ModuleBase::module_);
  }
  return v4;
}

```

## disassembly

```asm
0x14000b570  push    rbx
0x14000b572  sub     rsp, 20h
0x14000b576  mov     rax, [rcx+48h]
0x14000b57a  mov     r10, rcx
0x14000b57d  test    rax, rax
0x14000b580  js      short loc_14000B59E
0x14000b582  cmp     eax, 7FFFFFFFh
0x14000b587  jz      short loc_14000B597
0x14000b589  lea     rbx, [rax-1]
0x14000b58d  lock cmpxchg [rcx+48h], rbx
0x14000b593  jnz     short loc_14000B57D
0x14000b595  jmp     short loc_14000B5AD
0x14000b597  mov     ebx, 7FFFFFFEh
0x14000b59c  jmp     short loc_14000B5E0
0x14000b59e  lea     rcx, ds:10h[rax*2]; this
0x14000b5a6  call    ?SafeUnknownDecrementReference@Details@WRL@Microsoft@@YAKAECJ@Z; Microsoft::WRL::Details::SafeUnknownDecrementReference(long volatile &)
0x14000b5ab  mov     ebx, eax
0x14000b5ad  test    ebx, ebx
0x14000b5af  jnz     short loc_14000B5E0
0x14000b5b1  test    r10, r10
0x14000b5b4  jz      short loc_14000B5C8
0x14000b5b6  mov     rcx, [r10]
0x14000b5b9  lea     edx, [rbx+1]
0x14000b5bc  mov     rax, [rcx+48h]
0x14000b5c0  mov     rcx, r10
0x14000b5c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000b5c8  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x14000b5cf  test    rcx, rcx
0x14000b5d2  jz      short loc_14000B5E0
0x14000b5d4  mov     rax, [rcx]
0x14000b5d7  mov     rax, [rax+10h]
0x14000b5db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000b5e0  mov     eax, ebx
0x14000b5e2  add     rsp, 20h
0x14000b5e6  pop     rbx
0x14000b5e7  retn
```
