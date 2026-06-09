# GetCodecFactory(IWICComponentFactory * *)

- ea: `0x180004004`
- end: `0x1800040e0`
- name: `?GetCodecFactory@@YAJPEAPEAUIWICComponentFactory@@@Z`
- size: `220`
- prototype: `__int64 __fastcall(struct IWICComponentFactory **)`
- caller_count: `6`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180003350`
- `0x1800038e0`
- `0x180004530`
- `0x18001883c`
- `0x18001f224`
- `0x18001ff04`

## callees

- `0x180004004`
- `0x180022790`
- `0x180033010`

## pseudocode

```c
__int64 __fastcall GetCodecFactory(struct IWICComponentFactory **a1, __int64 a2, __int64 a3)
{
  struct IWICComponentFactory *v4; // rcx
  struct IWICComponentFactory v5; // rax
  int v7; // ebx
  void *v8; // [rsp+40h] [rbp+8h] BYREF
  signed __int64 v9; // [rsp+48h] [rbp+10h] BYREF

  *a1 = 0;
  v4 = g_pCodecFactory;
  if ( g_pCodecFactory )
  {
LABEL_2:
    v5.lpVtbl = v4->lpVtbl;
    *a1 = v4;
    ((void (*)(void))v5.lpVtbl->AddRef)();
    return 0;
  }
  v8 = 0;
  v7 = ComlessCoCreate(&CLSID_WICImagingFactoryCOMLess, &IID_IWICImagingFactory, a3, &v8);
  if ( v7 >= 0 )
  {
    v9 = 0;
    v7 = (**(__int64 (__fastcall ***)(void *, GUID *, signed __int64 *))v8)(v8, &IID_IWICComponentFactory, &v9);
    (*(void (__fastcall **)(void *))(*(_QWORD *)v8 + 16LL))(v8);
    if ( v7 >= 0 )
    {
      if ( _InterlockedCompareExchange64((volatile signed __int64 *)&g_pCodecFactory, v9, 0) )
      {
        if ( v9 )
          (*(void (__fastcall **)(signed __int64))(*(_QWORD *)v9 + 16LL))(v9);
      }
      v4 = g_pCodecFactory;
      goto LABEL_2;
    }
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180004004  mov     [rsp+arg_10], rbx
0x180004009  push    rdi
0x18000400a  sub     rsp, 30h
0x18000400e  mov     rdi, rcx
0x180004011  mov     qword ptr [rcx], 0
0x180004018  mov     rcx, cs:?g_pCodecFactory@@3PEAUIWICComponentFactory@@EA; IWICComponentFactory * g_pCodecFactory
0x18000401f  test    rcx, rcx
0x180004022  jz      short loc_18000405F
0x180004024  mov     rax, [rcx]
0x180004027  mov     [rdi], rcx
0x18000402a  mov     rax, [rax+8]
0x18000402e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004033  xor     eax, eax
0x180004035  mov     rbx, [rsp+38h+arg_10]
0x18000403a  add     rsp, 30h
0x18000403e  pop     rdi
0x18000403f  retn
0x180004040  mov     rcx, [rsp+38h+arg_8]
0x180004045  test    rcx, rcx
0x180004048  jz      short loc_180004056
0x18000404a  mov     rax, [rcx]
0x18000404d  mov     rax, [rax+10h]
0x180004051  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004056  mov     rcx, cs:?g_pCodecFactory@@3PEAUIWICComponentFactory@@EA; IWICComponentFactory * g_pCodecFactory
0x18000405d  jmp     short loc_180004024
0x18000405f  lea     r9, [rsp+38h+arg_0]; void **
0x180004064  mov     [rsp+38h+arg_0], 0
0x18000406d  lea     rdx, IID_IWICImagingFactory; struct _GUID *
0x180004074  lea     rcx, CLSID_WICImagingFactoryCOMLess; struct _GUID *
0x18000407b  call    ?ComlessCoCreate@@YAJAEBU_GUID@@0KPEAPEAXPEBGAEAU_COMLESS_CO_DLL_DATA@@@Z; ComlessCoCreate(_GUID const &,_GUID const &,ulong,void * *,ushort const *,_COMLESS_CO_DLL_DATA &)
0x180004080  mov     ebx, eax
0x180004082  test    eax, eax
0x180004084  js      short loc_1800040D9
0x180004086  mov     rcx, [rsp+38h+arg_0]
0x18000408b  lea     r8, [rsp+38h+arg_8]
0x180004090  mov     [rsp+38h+arg_8], 0
0x180004099  lea     rdx, IID_IWICComponentFactory
0x1800040a0  mov     rax, [rcx]
0x1800040a3  mov     rax, [rax]
0x1800040a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800040ab  mov     rcx, [rsp+38h+arg_0]
0x1800040b0  mov     ebx, eax
0x1800040b2  mov     rax, [rcx]
0x1800040b5  mov     rax, [rax+10h]
0x1800040b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800040be  test    ebx, ebx
0x1800040c0  js      short loc_1800040D9
0x1800040c2  mov     rcx, [rsp+38h+arg_8]
0x1800040c7  xor     eax, eax
0x1800040c9  lock cmpxchg cs:?g_pCodecFactory@@3PEAUIWICComponentFactory@@EA, rcx; IWICComponentFactory * g_pCodecFactory
0x1800040d2  jz      short loc_180004056
0x1800040d4  jmp     loc_180004040
0x1800040d9  mov     eax, ebx
0x1800040db  jmp     loc_180004035
```
