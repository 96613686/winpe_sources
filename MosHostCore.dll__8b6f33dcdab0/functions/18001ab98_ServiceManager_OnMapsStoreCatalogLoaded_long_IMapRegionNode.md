# ServiceManager::OnMapsStoreCatalogLoaded(long,IMapRegionNode *)

- ea: `0x18001ab98`
- end: `0x18001ac2d`
- name: `?OnMapsStoreCatalogLoaded@ServiceManager@@QEAAXJPEAVIMapRegionNode@@@Z`
- size: `149`
- prototype: `void(ServiceManager *__hidden this, int, struct IMapRegionNode *)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task`

## callers

- `0x1800114c0`

## callees

- `0x18000381c`
- `0x180010780`
- `0x180011ae4`
- `0x180012198`
- `0x18001ab98`
- `0x18001f3c4`

## pseudocode

```c
void __fastcall ServiceManager::OnMapsStoreCatalogLoaded(ServiceManager *this, int a2, struct IMapRegionNode *a3)
{
  struct _TP_CALLBACK_ENVIRON_V3 *v4; // rdi
  _OWORD *v5; // rbx
  _OWORD *v6; // rax
  _BYTE v7[24]; // [rsp+20h] [rbp-18h] BYREF
  void *v8; // [rsp+40h] [rbp+8h] BYREF
  int v9; // [rsp+48h] [rbp+10h] BYREF

  if ( a2 < 0 )
  {
    if ( a2 == -2080309236 )
      a2 = -2080374776;
    v9 = a2;
  }
  else
  {
    v9 = PackageManager::RegisterRegionNodeInformation((ServiceManager *)((char *)this + 3568), a3);
  }
  v4 = (struct _TP_CALLBACK_ENVIRON_V3 *)*((_QWORD *)this + 424);
  v5 = (_OWORD *)lambda_b73e6b330fc6e17daa98f76287d58a3d_::_lambda_b73e6b330fc6e17daa98f76287d58a3d_(v7, this, &v9);
  v6 = operator new(0x10u);
  *v6 = *v5;
  Threadpool::QueueWorkItem(v4, lambda_011fcb7d72eebd70e7ba40645b8db56e_::_lambda_invoker_cdecl_, v6);
  v8 = 0;
  std::unique_ptr__lambda_e0151e82603ed25fc2b10ac46ee2682c__std::default_delete__lambda_e0151e82603ed25fc2b10ac46ee2682c_____::_unique_ptr__lambda_e0151e82603ed25fc2b10ac46ee2682c__std::default_delete__lambda_e0151e82603ed25fc2b10ac46ee2682c_____(&v8);
}

```

## disassembly

```asm
0x18001ab98  mov     [rsp+arg_10], rbx
0x18001ab9d  push    rdi
0x18001ab9e  sub     rsp, 30h
0x18001aba2  mov     rbx, rcx
0x18001aba5  test    edx, edx
0x18001aba7  js      short loc_18001ABBE
0x18001aba9  add     rcx, 0DF0h; this
0x18001abb0  mov     rdx, r8; struct IMapRegionNode *
0x18001abb3  call    ?RegisterRegionNodeInformation@PackageManager@@QEAAJPEAVIMapRegionNode@@@Z; PackageManager::RegisterRegionNodeInformation(IMapRegionNode *)
0x18001abb8  mov     [rsp+38h+arg_8], eax
0x18001abbc  jmp     short loc_18001ABD0
0x18001abbe  cmp     edx, 8401000Ch
0x18001abc4  mov     eax, 84000008h
0x18001abc9  cmovz   edx, eax
0x18001abcc  mov     [rsp+38h+arg_8], edx
0x18001abd0  mov     rdi, [rbx+0D40h]
0x18001abd7  lea     r8, [rsp+38h+arg_8]
0x18001abdc  mov     rdx, rbx
0x18001abdf  lea     rcx, [rsp+38h+var_18]
0x18001abe4  call    _lambda_b73e6b330fc6e17daa98f76287d58a3d____lambda_b73e6b330fc6e17daa98f76287d58a3d_
0x18001abe9  mov     ecx, 10h; Size
0x18001abee  mov     rbx, rax
0x18001abf1  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001abf6  movups  xmm0, xmmword ptr [rbx]
0x18001abf9  mov     r8, rax; pv
0x18001abfc  lea     rdx, _lambda_011fcb7d72eebd70e7ba40645b8db56e____lambda_invoker_cdecl_; pfnwk
0x18001ac03  mov     rcx, rdi; pcbe
0x18001ac06  movdqu  xmmword ptr [rax], xmm0
0x18001ac0a  call    ?QueueWorkItem@Threadpool@@AEAAXP6AXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z1@Z; Threadpool::QueueWorkItem(void (*)(_TP_CALLBACK_INSTANCE *,void *,_TP_WORK *),void *)
0x18001ac0f  lea     rcx, [rsp+38h+arg_0]
0x18001ac14  mov     [rsp+38h+arg_0], 0
0x18001ac1d  call    std__unique_ptr__lambda_e0151e82603ed25fc2b10ac46ee2682c__std__default_delete__lambda_e0151e82603ed25fc2b10ac46ee2682c________unique_ptr__lambda_e0151e82603ed25fc2b10ac46ee2682c__std__default_delete__lambda_e0151e82603ed25fc2b10ac46ee2682c_____
0x18001ac22  mov     rbx, [rsp+38h+arg_10]
0x18001ac27  add     rsp, 30h
0x18001ac2b  pop     rdi
0x18001ac2c  retn
```
