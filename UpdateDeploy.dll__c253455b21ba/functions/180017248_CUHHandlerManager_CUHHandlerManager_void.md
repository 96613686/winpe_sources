# CUHHandlerManager::~CUHHandlerManager(void)

- ea: `0x180017248`
- end: `0x180017330`
- name: `??1CUHHandlerManager@@UEAA@XZ`
- size: `232`
- prototype: `void(CUHHandlerManager *__hidden this)`
- caller_count: `5`
- callee_count: `6`
- tags: `loader_planting, installer_update`

## callers

- `0x180006be0`
- `0x180013494`
- `0x1800171ec`
- `0x180028944`
- `0x180069e42`

## callees

- `0x180007b6c`
- `0x180017248`
- `0x180018400`
- `0x18001aa6c`
- `0x18001ab34`
- `0x180068ea0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180017307`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180017307`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800172e3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800172e3`

## string_xrefs

- `0x18001728c`: `C:\__w\1\s\src\Client\UpdateDeployment\Lib\uhmgr.cpp`

## pseudocode

```c
void __fastcall CUHHandlerManager::~CUHHandlerManager(CUHHandlerManager *this)
{
  char *v2; // rdi
  int v3; // eax
  _QWORD *v4; // rdi
  __int64 v5; // rsi
  void *v6; // rcx
  int v7; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  *(_QWORD *)this = &CUHHandlerManager::`vftable'{for `ISusCreateRemoteHandler'};
  *((_QWORD *)this + 1) = &CUHHandlerManager::`vftable'{for `CSusBaseAllocTag<1127245941>'};
  if ( *((_BYTE *)this + 40) )
  {
    v3 = CUHHandlerManager::ReleaseRemoteProcess(this);
    if ( v3 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x14B,
        (unsigned int)"C:\\__w\\1\\s\\src\\Client\\UpdateDeployment\\Lib\\uhmgr.cpp",
        (const char *)(unsigned int)v3,
        v7);
    v4 = (_QWORD *)((char *)this + 104);
    v5 = 13;
    do
    {
      if ( *v4 )
        (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v4 + 16LL))(*v4);
      *v4++ = 0;
      --v5;
    }
    while ( v5 );
    v2 = (char *)this + 16;
    CSusArrayList<CUHPlugin *,CSusArrayListItemOpDelete<CUHPlugin *>>::RemoveArraySection((char *)this + 16);
    v6 = (void *)*((_QWORD *)this + 42);
    if ( v6 )
      CloseHandle(v6);
    *((_QWORD *)this + 42) = 0;
    *((_BYTE *)this + 40) = 0;
  }
  else
  {
    v2 = (char *)this + 16;
  }
  *((_QWORD *)this + 7) = &CSusLock::`vftable';
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 64));
  CSusArrayList<CUHPlugin *,CSusArrayListItemOpDelete<CUHPlugin *>>::~CSusArrayList<CUHPlugin *,CSusArrayListItemOpDelete<CUHPlugin *>>(v2);
  *((_QWORD *)this + 1) = &CSusBaseAllocTag<1127245941>::`vftable';
}

```

## disassembly

```asm
0x180017248  mov     [rsp+arg_0], rbx
0x18001724d  mov     [rsp+arg_8], rsi
0x180017252  push    rdi; int
0x180017253  sub     rsp, 20h
0x180017257  mov     rbx, rcx
0x18001725a  lea     rax, ??_7CUHHandlerManager@@6BISusCreateRemoteHandler@@@; const CUHHandlerManager::`vftable'{for `ISusCreateRemoteHandler'}
0x180017261  mov     [rcx], rax
0x180017264  lea     rax, ??_7CUHHandlerManager@@6B?$CSusBaseAllocTag@$0EDDAGIHF@@@@; const CUHHandlerManager::`vftable'{for `CSusBaseAllocTag<1127245941>'}
0x18001726b  mov     [rcx+8], rax
0x18001726f  cmp     byte ptr [rcx+28h], 0
0x180017273  jnz     short loc_18001727B
0x180017275  lea     rdi, [rcx+10h]
0x180017279  jmp     short loc_1800172F8
0x18001727b  call    ?ReleaseRemoteProcess@CUHHandlerManager@@AEAAJXZ; CUHHandlerManager::ReleaseRemoteProcess(void)
0x180017280  test    eax, eax
0x180017282  jns     short loc_18001729D
0x180017284  mov     rcx, [rsp+28h]; this
0x180017289  mov     r9d, eax; char *
0x18001728c  lea     r8, aCW1SSrcClientU_4; "C:\\__w\\1\\s\\src\\Client\\UpdateDeplo"...
0x180017293  mov     edx, 14Bh; void *
0x180017298  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18001729d  lea     rdi, [rbx+68h]
0x1800172a1  mov     esi, 0Dh
0x1800172a6  mov     rcx, [rdi]
0x1800172a9  test    rcx, rcx
0x1800172ac  jz      short loc_1800172BA
0x1800172ae  mov     rax, [rcx]
0x1800172b1  mov     rax, [rax+10h]
0x1800172b5  call    _guard_dispatch_icall
0x1800172ba  mov     qword ptr [rdi], 0
0x1800172c1  add     rdi, 8
0x1800172c5  sub     rsi, 1
0x1800172c9  jnz     short loc_1800172A6
0x1800172cb  lea     rdi, [rbx+10h]
0x1800172cf  mov     rcx, rdi
0x1800172d2  call    ?RemoveArraySection@?$CSusArrayList@PEAVCUHPlugin@@V?$CSusArrayListItemOpDelete@PEAVCUHPlugin@@@@@@IEAAXKKH@Z; CSusArrayList<CUHPlugin *,CSusArrayListItemOpDelete<CUHPlugin *>>::RemoveArraySection(ulong,ulong,int)
0x1800172d7  mov     rcx, [rbx+150h]; hObject
0x1800172de  test    rcx, rcx
0x1800172e1  jz      short loc_1800172E9
0x1800172e3  call    cs:__imp_CloseHandle
0x1800172e9  mov     qword ptr [rbx+150h], 0
0x1800172f4  mov     byte ptr [rbx+28h], 0
0x1800172f8  lea     rax, ??_7CSusLock@@6B@; const CSusLock::`vftable'
0x1800172ff  mov     [rbx+38h], rax
0x180017303  lea     rcx, [rbx+40h]; lpCriticalSection
0x180017307  call    cs:__imp_DeleteCriticalSection
0x18001730d  mov     rcx, rdi
0x180017310  call    ??1?$CSusArrayList@PEAVCUHPlugin@@V?$CSusArrayListItemOpDelete@PEAVCUHPlugin@@@@@@UEAA@XZ; CSusArrayList<CUHPlugin *,CSusArrayListItemOpDelete<CUHPlugin *>>::~CSusArrayList<CUHPlugin *,CSusArrayListItemOpDelete<CUHPlugin *>>(void)
0x180017315  lea     rax, ??_7?$CSusBaseAllocTag@$0EDDAGIHF@@@6B@; const CSusBaseAllocTag<1127245941>::`vftable'
0x18001731c  mov     [rbx+8], rax
0x180017320  mov     rbx, [rsp+28h+arg_0]
0x180017325  mov     rsi, [rsp+28h+arg_8]
0x18001732a  add     rsp, 20h
0x18001732e  pop     rdi
0x18001732f  retn
```
