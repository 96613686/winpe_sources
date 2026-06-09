# CMetadataRDFReaderWriter::GetMetadataHandlerInfo(IWICMetadataHandlerInfo * *)

- ea: `0x180004530`
- end: `0x18000464a`
- name: `?GetMetadataHandlerInfo@CMetadataRDFReaderWriter@@UEAAJPEAPEAUIWICMetadataHandlerInfo@@@Z`
- size: `282`
- prototype: `__int64 __fastcall(CMetadataRDFReaderWriter *__hidden this, struct IWICMetadataHandlerInfo **)`
- caller_count: `0`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180004004`
- `0x180004530`
- `0x1800058c0`
- `0x1800058e0`
- `0x1800171c4`
- `0x180033010`

## pseudocode

```c
__int64 __fastcall CMetadataRDFReaderWriter::GetMetadataHandlerInfo(
        CMetadataRDFReaderWriter *this,
        struct IWICMetadataHandlerInfo **a2)
{
  CMTALock *v2; // rsi
  __int64 v5; // rdx
  __int64 v6; // r8
  int CodecFactory; // eax
  struct IWICComponentFactory *v8; // rdi
  unsigned int v9; // ebx
  int v11; // ecx
  __int64 v12; // [rsp+40h] [rbp+8h] BYREF
  struct IWICComponentFactory *v13; // [rsp+50h] [rbp+18h] BYREF

  v2 = (CMetadataRDFReaderWriter *)((char *)this + 40);
  v12 = 0;
  v13 = 0;
  CMTALock::Enter((CMetadataRDFReaderWriter *)((char *)this + 40));
  CodecFactory = GetCodecFactory(&v13, v5, v6);
  v8 = v13;
  v9 = CodecFactory;
  if ( CodecFactory < 0 )
    goto LABEL_2;
  if ( a2 )
  {
    CodecFactory = ((__int64 (__fastcall *)(struct IWICComponentFactory *, _QWORD, __int64 *))v13->lpVtbl->CreateComponentInfo)(
                     v13,
                     *((_QWORD *)this + 20),
                     &v12);
    v9 = CodecFactory;
    if ( CodecFactory < 0
      || (CodecFactory = (**(__int64 (__fastcall ***)(__int64, GUID *, struct IWICMetadataHandlerInfo **))v12)(
                           v12,
                           &IID_IWICMetadataHandlerInfo,
                           a2),
          v9 = CodecFactory,
          CodecFactory < 0) )
    {
LABEL_2:
      if ( !g_doStackCaptures )
        goto LABEL_3;
      v11 = CodecFactory;
      goto LABEL_11;
    }
  }
  else
  {
    v9 = -2147024809;
    if ( g_doStackCaptures )
    {
      v11 = -2147024809;
LABEL_11:
      DoStackCapture(v11);
    }
  }
LABEL_3:
  if ( v8 )
    ((void (__fastcall *)(struct IWICComponentFactory *))v8->lpVtbl->Release)(v8);
  if ( v12 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
    v12 = 0;
  }
  if ( v2 )
    CMTALock::Leave(v2);
  return v9;
}

```

## disassembly

```asm
0x180004530  mov     rax, rsp
0x180004533  mov     [rax+10h], rbx
0x180004537  mov     [rax+20h], rbp
0x18000453b  push    rsi
0x18000453c  push    rdi
0x18000453d  push    r14
0x18000453f  sub     rsp, 20h
0x180004543  lea     rsi, [rcx+28h]
0x180004547  mov     qword ptr [rax+8], 0
0x18000454f  mov     r14, rcx
0x180004552  mov     qword ptr [rax+18h], 0
0x18000455a  mov     rcx, rsi; this
0x18000455d  mov     rbp, rdx
0x180004560  call    ?Enter@CMTALock@@QEAAXXZ; CMTALock::Enter(void)
0x180004565  lea     rcx, [rsp+38h+arg_10]; struct IWICComponentFactory **
0x18000456a  call    ?GetCodecFactory@@YAJPEAPEAUIWICComponentFactory@@@Z; GetCodecFactory(IWICComponentFactory * *)
0x18000456f  mov     rdi, [rsp+38h+arg_10]
0x180004574  mov     ebx, eax
0x180004576  test    eax, eax
0x180004578  jns     short loc_1800045E1
0x18000457a  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x180004581  jnz     short loc_1800045D8
0x180004583  test    rdi, rdi
0x180004586  jz      short loc_180004597
0x180004588  mov     rax, [rdi]
0x18000458b  mov     rcx, rdi
0x18000458e  mov     rax, [rax+10h]
0x180004592  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004597  mov     rcx, [rsp+38h+arg_0]
0x18000459c  test    rcx, rcx
0x18000459f  jz      short loc_1800045B6
0x1800045a1  mov     rax, [rcx]
0x1800045a4  mov     rax, [rax+10h]
0x1800045a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800045ad  mov     [rsp+38h+arg_0], 0
0x1800045b6  test    rsi, rsi
0x1800045b9  jz      short loc_1800045C3
0x1800045bb  mov     rcx, rsi; this
0x1800045be  call    ?Leave@CMTALock@@QEAAXXZ; CMTALock::Leave(void)
0x1800045c3  mov     rbp, [rsp+38h+arg_18]
0x1800045c8  mov     eax, ebx
0x1800045ca  mov     rbx, [rsp+38h+arg_8]
0x1800045cf  add     rsp, 20h
0x1800045d3  pop     r14
0x1800045d5  pop     rdi
0x1800045d6  pop     rsi
0x1800045d7  retn
0x1800045d8  mov     ecx, eax; int
0x1800045da  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x1800045df  jmp     short loc_180004583
0x1800045e1  test    rbp, rbp
0x1800045e4  jz      short loc_180004634
0x1800045e6  mov     rax, [rdi]
0x1800045e9  lea     r8, [rsp+38h+arg_0]
0x1800045ee  mov     rdx, [r14+0A0h]
0x1800045f5  mov     rcx, rdi
0x1800045f8  mov     rax, [rax+30h]
0x1800045fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004601  mov     ebx, eax
0x180004603  test    eax, eax
0x180004605  js      loc_18000457A
0x18000460b  mov     rcx, [rsp+38h+arg_0]
0x180004610  lea     rdx, IID_IWICMetadataHandlerInfo
0x180004617  mov     r8, rbp
0x18000461a  mov     rax, [rcx]
0x18000461d  mov     rax, [rax]
0x180004620  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004625  mov     ebx, eax
0x180004627  test    eax, eax
0x180004629  js      loc_18000457A
0x18000462f  jmp     loc_180004583
0x180004634  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x18000463b  mov     ebx, 80070057h
0x180004640  jz      loc_180004583
0x180004646  mov     ecx, ebx
0x180004648  jmp     short loc_1800045DA
```
