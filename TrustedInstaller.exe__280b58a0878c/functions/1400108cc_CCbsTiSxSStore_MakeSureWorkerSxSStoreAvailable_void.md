# CCbsTiSxSStore::MakeSureWorkerSxSStoreAvailable(void)

- ea: `0x1400108cc`
- end: `0x140010939`
- name: `?MakeSureWorkerSxSStoreAvailable@CCbsTiSxSStore@@AEAAJXZ`
- size: `109`
- prototype: `__int64 __fastcall(CCbsTiSxSStore *__hidden this)`
- caller_count: `4`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x14000ede4`
- `0x14000f634`
- `0x1400104a4`
- `0x140012a74`

## callees

- `0x140006778`
- `0x140007630`
- `0x14000e2ac`
- `0x1400108cc`
- `0x140014d60`
- `0x140017658`

## string_xrefs

- `0x14001090e`: `Failed to create worker SxS store.`

## pseudocode

```c
__int64 __fastcall CCbsTiSxSStore::MakeSureWorkerSxSStoreAvailable(CCbsTiSxSStore *this)
{
  _QWORD *v2; // rcx
  unsigned int v3; // ebx
  CCbsPublicSessionClassFactory *v4; // rbx
  void **InitPointer; // rax
  const struct _GUID *v6; // rdx
  int NonSessionObject; // eax
  _BYTE v9[40]; // [rsp+20h] [rbp-28h] BYREF

  CritSecLocker::CritSecLocker((CritSecLocker *)v9, (CCbsTiSxSStore *)((char *)this + 32), 1);
  v2 = (_QWORD *)((char *)this + 72);
  if ( *((_QWORD *)this + 9) )
  {
    v3 = 0;
  }
  else
  {
    v4 = (CCbsPublicSessionClassFactory *)*((_QWORD *)this + 3);
    InitPointer = (void **)Windows::AutoComPtr<IClassFactory>::GetInitPointer(v2);
    NonSessionObject = CCbsPublicSessionClassFactory::CreateNonSessionObject(v4, v6, InitPointer);
    v3 = NonSessionObject;
    if ( NonSessionObject < 0 )
      CBSWdsLogLight(0x4000000u, (unsigned int)NonSessionObject, (size_t *)1, "Failed to create worker SxS store.");
  }
  CritSecLocker::~CritSecLocker((CritSecLocker *)v9);
  return v3;
}

```

## disassembly

```asm
0x1400108cc  push    rbx
0x1400108ce  sub     rsp, 40h
0x1400108d2  mov     rbx, rcx
0x1400108d5  lea     rdx, [rcx+20h]; struct AutoCritSec *
0x1400108d9  lea     rcx, [rsp+48h+var_28]; this
0x1400108de  mov     r8b, 1; bool
0x1400108e1  call    ??0CritSecLocker@@QEAA@AEAVAutoCritSec@@_N@Z; CritSecLocker::CritSecLocker(AutoCritSec &,bool)
0x1400108e6  lea     rcx, [rbx+48h]
0x1400108ea  cmp     qword ptr [rcx], 0
0x1400108ee  jz      short loc_1400108F4
0x1400108f0  xor     ebx, ebx
0x1400108f2  jmp     short loc_140010927
0x1400108f4  mov     rbx, [rbx+18h]
0x1400108f8  call    ?GetInitPointer@?$AutoComPtr@UIClassFactory@@@Windows@@QEAAPEAPEAUIClassFactory@@XZ; Windows::AutoComPtr<IClassFactory>::GetInitPointer(void)
0x1400108fd  mov     r8, rax; void **
0x140010900  mov     rcx, rbx; this
0x140010903  call    ?CreateNonSessionObject@CCbsPublicSessionClassFactory@@QEAAJAEBU_GUID@@PEAPEAX@Z; CCbsPublicSessionClassFactory::CreateNonSessionObject(_GUID const &,void * *)
0x140010908  mov     ebx, eax
0x14001090a  test    eax, eax
0x14001090c  jns     short loc_140010927
0x14001090e  lea     r9, aFailedToCreate_20; "Failed to create worker SxS store."
0x140010915  mov     r8d, 1
0x14001091b  mov     edx, eax
0x14001091d  mov     ecx, 4000000h
0x140010922  call    ?CBSWdsLogLight@@YAXW4tagLOG_SETUPLOG_SEVERITY@@J_NPEBDZZ; CBSWdsLogLight(tagLOG_SETUPLOG_SEVERITY,long,bool,char const *,...)
0x140010927  lea     rcx, [rsp+48h+var_28]; this
0x14001092c  call    ??1CritSecLocker@@UEAA@XZ; CritSecLocker::~CritSecLocker(void)
0x140010931  mov     eax, ebx
0x140010933  add     rsp, 40h
0x140010937  pop     rbx
0x140010938  retn
```
