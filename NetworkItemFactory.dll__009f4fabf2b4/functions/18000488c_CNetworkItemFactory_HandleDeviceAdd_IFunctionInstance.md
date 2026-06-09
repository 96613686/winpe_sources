# CNetworkItemFactory::_HandleDeviceAdd(IFunctionInstance *)

- ea: `0x18000488c`
- end: `0x1800049ee`
- name: `?_HandleDeviceAdd@CNetworkItemFactory@@AEAAJPEAUIFunctionInstance@@@Z`
- size: `354`
- prototype: `__int64 __fastcall(CNetworkItemFactory *__hidden this, struct IFunctionInstance *)`
- caller_count: `2`
- callee_count: `9`
- tags: `installer_update`

## callers

- `0x180003470`
- `0x1800037f8`

## callees

- `0x180003ca0`
- `0x180003d28`
- `0x180004074`
- `0x18000488c`
- `0x180004fb0`
- `0x18000531c`
- `0x18000568c`
- `0x180008638`
- `0x18000b010`

## pseudocode

```c
__int64 __fastcall CNetworkItemFactory::_HandleDeviceAdd(CNetworkItemFactory *this, struct IFunctionInstance *a2)
{
  __int64 v2; // rdi
  unsigned int v5; // r8d
  __int64 v6; // rdx
  __int64 v7; // rcx
  __int64 v9; // rbx
  __int64 v10; // rcx
  int updated; // edi
  struct INetworkItem *v12; // r14
  struct INetworkItem *v13; // rbx
  __int64 v14; // rax
  struct INetworkItem *v15; // rcx
  int v16; // ebx
  struct INetworkItem *v17; // rbx
  struct INetworkItem *v18; // [rsp+50h] [rbp+30h] BYREF
  struct INetworkItem *v19; // [rsp+60h] [rbp+40h] BYREF

  v2 = *((_QWORD *)this + 10);
  if ( *(_DWORD *)(v2 + 20) )
  {
    v5 = 0;
    v6 = 0;
    do
    {
      v7 = *(_QWORD *)(*(_QWORD *)(v2 + 24) + 8 * v6);
      v6 = (unsigned int)(v6 + 1);
      v5 += *(_DWORD *)(v7 + 120);
    }
    while ( (unsigned int)v6 < *(_DWORD *)(v2 + 20) );
    if ( v5 > 0x7D00 )
      return 2147500037LL;
    v9 = 0;
    do
    {
      v10 = *(_QWORD *)(*(_QWORD *)(v2 + 24) + 8 * v9);
      if ( *(_BYTE *)(v10 + 153) )
        CReaderWriterLock3::WriteLock((CReaderWriterLock3 *)(v10 + 24));
      v9 = (unsigned int)(v9 + 1);
    }
    while ( (unsigned int)v9 < *(_DWORD *)(v2 + 20) );
  }
  LODWORD(v18) = 0;
  v19 = 0;
  updated = CNetworkItemFactory::_DuplicateDetection(this, a2, &v19, (int *)&v18);
  if ( updated >= 0 )
  {
    v12 = v19;
    if ( v19 )
    {
      if ( (_DWORD)v18 || (v16 = *((_DWORD *)v19 + 30), (int)CNetworkItemFactory::s_GetFIPriority(a2) > v16) )
      {
        v18 = 0;
        updated = CNetworkItemFactory::_UpdateActiveItem(this, v12, a2, &v18);
        if ( updated >= 0 )
        {
          v17 = v18;
          CNetworkItemFactory::_SendNotification(this, 0x2000, v18);
          (*(void (__fastcall **)(struct INetworkItem *))(*(_QWORD *)v17 + 16LL))(v17);
        }
      }
      v14 = *(_QWORD *)v12;
      v15 = v12;
      goto LABEL_19;
    }
    v18 = 0;
    updated = CNetworkItemFactory::_AddNewItem(this, a2, &v18);
    if ( updated >= 0 )
    {
      v13 = v18;
      CNetworkItemFactory::_SendNotification(this, 2, v18);
      v14 = *(_QWORD *)v13;
      v15 = v13;
LABEL_19:
      (*(void (__fastcall **)(struct INetworkItem *))(v14 + 16))(v15);
    }
  }
  LKRhash::CLKRHashTable::WriteUnlock(*((LKRhash::CLKRHashTable **)this + 10));
  return (unsigned int)updated;
}

```

## disassembly

```asm
0x18000488c  mov     [rsp-28h+arg_8], rbx
0x180004891  push    rbp
0x180004892  push    rsi
0x180004893  push    rdi
0x180004894  push    r14
0x180004896  push    r15
0x180004898  mov     rbp, rsp
0x18000489b  sub     rsp, 20h
0x18000489f  mov     rdi, [rcx+50h]
0x1800048a3  mov     r15, rdx
0x1800048a6  mov     rsi, rcx
0x1800048a9  cmp     dword ptr [rdi+14h], 0
0x1800048ad  jbe     short loc_1800048FD
0x1800048af  mov     r9, [rdi+18h]
0x1800048b3  xor     r8d, r8d
0x1800048b6  xor     edx, edx
0x1800048b8  mov     rcx, [r9+rdx*8]
0x1800048bc  inc     edx
0x1800048be  add     r8d, [rcx+78h]
0x1800048c2  cmp     edx, [rdi+14h]
0x1800048c5  jb      short loc_1800048B8
0x1800048c7  cmp     r8d, 7D00h
0x1800048ce  jbe     short loc_1800048DA
0x1800048d0  mov     eax, 80004005h
0x1800048d5  jmp     loc_1800049DD
0x1800048da  xor     ebx, ebx
0x1800048dc  mov     rax, [rdi+18h]
0x1800048e0  mov     rcx, [rax+rbx*8]
0x1800048e4  cmp     byte ptr [rcx+99h], 0
0x1800048eb  jz      short loc_1800048F6
0x1800048ed  add     rcx, 18h; this
0x1800048f1  call    ?WriteLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteLock(void)
0x1800048f6  inc     ebx
0x1800048f8  cmp     ebx, [rdi+14h]
0x1800048fb  jb      short loc_1800048DC
0x1800048fd  lea     r9, [rbp+arg_0]; int *
0x180004901  mov     dword ptr [rbp+arg_0], 0
0x180004908  lea     r8, [rbp+arg_10]; struct CNetworkItem **
0x18000490c  mov     [rbp+arg_10], 0
0x180004914  mov     rdx, r15; struct IFunctionInstance *
0x180004917  mov     rcx, rsi; this
0x18000491a  call    ?_DuplicateDetection@CNetworkItemFactory@@AEAAJPEAUIFunctionInstance@@PEAPEAVCNetworkItem@@PEAH@Z; CNetworkItemFactory::_DuplicateDetection(IFunctionInstance *,CNetworkItem * *,int *)
0x18000491f  mov     edi, eax
0x180004921  test    eax, eax
0x180004923  js      loc_1800049D2
0x180004929  mov     r14, [rbp+arg_10]
0x18000492d  test    r14, r14
0x180004930  jnz     short loc_18000496A
0x180004932  lea     r8, [rbp+arg_0]; struct CNetworkItem **
0x180004936  mov     [rbp+arg_0], r14
0x18000493a  mov     rdx, r15; struct IFunctionInstance *
0x18000493d  mov     rcx, rsi; this
0x180004940  call    ?_AddNewItem@CNetworkItemFactory@@AEAAJPEAUIFunctionInstance@@PEAPEAVCNetworkItem@@@Z; CNetworkItemFactory::_AddNewItem(IFunctionInstance *,CNetworkItem * *)
0x180004945  mov     edi, eax
0x180004947  test    eax, eax
0x180004949  js      loc_1800049D2
0x18000494f  mov     rbx, [rbp+arg_0]
0x180004953  lea     edx, [r14+2]; int
0x180004957  mov     r8, rbx; struct INetworkItem *
0x18000495a  mov     rcx, rsi; this
0x18000495d  call    ?_SendNotification@CNetworkItemFactory@@AEAAJJPEAUINetworkItem@@@Z; CNetworkItemFactory::_SendNotification(long,INetworkItem *)
0x180004962  mov     rax, [rbx]
0x180004965  mov     rcx, rbx
0x180004968  jmp     short loc_1800049C9
0x18000496a  cmp     dword ptr [rbp+arg_0], 0
0x18000496e  jnz     short loc_180004980
0x180004970  mov     ebx, [r14+78h]
0x180004974  mov     rcx, r15; struct IFunctionInstance *
0x180004977  call    ?s_GetFIPriority@CNetworkItemFactory@@SAHPEAUIFunctionInstance@@@Z; CNetworkItemFactory::s_GetFIPriority(IFunctionInstance *)
0x18000497c  cmp     eax, ebx
0x18000497e  jle     short loc_1800049C3
0x180004980  lea     r9, [rbp+arg_0]; struct CNetworkItem **
0x180004984  mov     [rbp+arg_0], 0
0x18000498c  mov     r8, r15; struct IFunctionInstance *
0x18000498f  mov     rdx, r14; struct INetworkItem *
0x180004992  mov     rcx, rsi; this
0x180004995  call    ?_UpdateActiveItem@CNetworkItemFactory@@AEAAJPEAUINetworkItem@@PEAUIFunctionInstance@@PEAPEAVCNetworkItem@@@Z; CNetworkItemFactory::_UpdateActiveItem(INetworkItem *,IFunctionInstance *,CNetworkItem * *)
0x18000499a  mov     edi, eax
0x18000499c  test    eax, eax
0x18000499e  js      short loc_1800049C3
0x1800049a0  mov     rbx, [rbp+arg_0]
0x1800049a4  mov     edx, 2000h; int
0x1800049a9  mov     r8, rbx; struct INetworkItem *
0x1800049ac  mov     rcx, rsi; this
0x1800049af  call    ?_SendNotification@CNetworkItemFactory@@AEAAJJPEAUINetworkItem@@@Z; CNetworkItemFactory::_SendNotification(long,INetworkItem *)
0x1800049b4  mov     rax, [rbx]
0x1800049b7  mov     rcx, rbx
0x1800049ba  mov     rax, [rax+10h]
0x1800049be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800049c3  mov     rax, [r14]
0x1800049c6  mov     rcx, r14
0x1800049c9  mov     rax, [rax+10h]
0x1800049cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800049d2  mov     rcx, [rsi+50h]; this
0x1800049d6  call    ?WriteUnlock@CLKRHashTable@LKRhash@@QEBAXXZ; LKRhash::CLKRHashTable::WriteUnlock(void)
0x1800049db  mov     eax, edi
0x1800049dd  mov     rbx, [rsp+20h+arg_8]
0x1800049e2  add     rsp, 20h
0x1800049e6  pop     r15
0x1800049e8  pop     r14
0x1800049ea  pop     rdi
0x1800049eb  pop     rsi
0x1800049ec  pop     rbp
0x1800049ed  retn
```
