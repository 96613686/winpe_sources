# CHandlerCache::_Init(void)

- ea: `0x1800155a0`
- end: `0x180015667`
- name: `?_Init@CHandlerCache@@AEAAJXZ`
- size: `199`
- prototype: `__int64 __fastcall(CHandlerCache *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callers

- `0x180004c70`

## callees

- `0x180005c10`
- `0x180012e54`
- `0x180013ab0`
- `0x1800155a0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800155e0`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180015609`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800155e0`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180015609`
- `api-ms-win-core-synch-l1-2-1!CreateWaitableTimerW` at `0x18001562f`
- `api-ms-win-core-synch-l1-2-1!CreateWaitableTimerW` at `0x18001562f`

## pseudocode

```c
__int64 __fastcall CHandlerCache::_Init(CHandlerCache *this)
{
  int Error; // ebx
  HANDLE EventW; // rax
  HANDLE v4; // rax
  HANDLE WaitableTimerW; // rax

  Error = -2147024882;
  if ( (unsigned int)CDPA_Base<ISyncClientFolderItem,CTContainer_PolicyUnOwned<ISyncClientFolderItem>>::Create((char *)this + 40) )
  {
    if ( (unsigned int)CDPA_Base<ISyncClientFolderItem,CTContainer_PolicyUnOwned<ISyncClientFolderItem>>::Create((char *)this + 48) )
    {
      EventW = CreateEventW(0, 1, 0, 0);
      *((_QWORD *)this + 51) = EventW;
      if ( EventW || (Error = ResultFromKnownLastError(), Error >= 0) )
      {
        v4 = CreateEventW(0, 1, 0, 0);
        *((_QWORD *)this + 52) = v4;
        if ( v4 || (Error = ResultFromKnownLastError(), Error >= 0) )
        {
          WaitableTimerW = CreateWaitableTimerW(0, 1, 0);
          *((_QWORD *)this + 54) = WaitableTimerW;
          if ( WaitableTimerW )
            return (unsigned int)CSyncTrayIconManager_CreateInstance((struct CSyncTrayIconManager **)this + 55);
          Error = ResultFromKnownLastError();
          if ( Error >= 0 )
            return (unsigned int)CSyncTrayIconManager_CreateInstance((struct CSyncTrayIconManager **)this + 55);
        }
      }
    }
  }
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x1800155a0  mov     [rsp+arg_0], rbx
0x1800155a5  push    rdi
0x1800155a6  sub     rsp, 20h
0x1800155aa  mov     rdi, rcx
0x1800155ad  mov     ebx, 8007000Eh
0x1800155b2  add     rcx, 28h ; '('
0x1800155b6  call    ?Create@?$CDPA_Base@UISyncClientFolderItem@@V?$CTContainer_PolicyUnOwned@UISyncClientFolderItem@@@@@@QEAAHH@Z; CDPA_Base<ISyncClientFolderItem,CTContainer_PolicyUnOwned<ISyncClientFolderItem>>::Create(int)
0x1800155bb  test    eax, eax
0x1800155bd  jz      loc_18001565A
0x1800155c3  lea     rcx, [rdi+30h]
0x1800155c7  call    ?Create@?$CDPA_Base@UISyncClientFolderItem@@V?$CTContainer_PolicyUnOwned@UISyncClientFolderItem@@@@@@QEAAHH@Z; CDPA_Base<ISyncClientFolderItem,CTContainer_PolicyUnOwned<ISyncClientFolderItem>>::Create(int)
0x1800155cc  test    eax, eax
0x1800155ce  jz      loc_18001565A
0x1800155d4  xor     r9d, r9d; lpName
0x1800155d7  xor     r8d, r8d; bInitialState
0x1800155da  xor     ecx, ecx; lpEventAttributes
0x1800155dc  lea     edx, [r9+1]; bManualReset
0x1800155e0  call    cs:__imp_CreateEventW
0x1800155e6  mov     [rdi+198h], rax
0x1800155ed  test    rax, rax
0x1800155f0  jnz     short loc_1800155FD
0x1800155f2  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1800155f7  mov     ebx, eax
0x1800155f9  test    eax, eax
0x1800155fb  js      short loc_18001565A
0x1800155fd  xor     r9d, r9d; lpName
0x180015600  xor     r8d, r8d; bInitialState
0x180015603  xor     ecx, ecx; lpEventAttributes
0x180015605  lea     edx, [r9+1]; bManualReset
0x180015609  call    cs:__imp_CreateEventW
0x18001560f  mov     [rdi+1A0h], rax
0x180015616  test    rax, rax
0x180015619  jnz     short loc_180015626
0x18001561b  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180015620  mov     ebx, eax
0x180015622  test    eax, eax
0x180015624  js      short loc_18001565A
0x180015626  xor     r8d, r8d; lpTimerName
0x180015629  xor     ecx, ecx; lpTimerAttributes
0x18001562b  lea     edx, [r8+1]; bManualReset
0x18001562f  call    cs:__imp_CreateWaitableTimerW
0x180015635  mov     [rdi+1B0h], rax
0x18001563c  test    rax, rax
0x18001563f  jnz     short loc_18001564C
0x180015641  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180015646  mov     ebx, eax
0x180015648  test    eax, eax
0x18001564a  js      short loc_18001565A
0x18001564c  lea     rcx, [rdi+1B8h]; struct CSyncTrayIconManager **
0x180015653  call    ?CSyncTrayIconManager_CreateInstance@@YAJPEAPEAVCSyncTrayIconManager@@@Z; CSyncTrayIconManager_CreateInstance(CSyncTrayIconManager * *)
0x180015658  mov     ebx, eax
0x18001565a  mov     eax, ebx
0x18001565c  mov     rbx, [rsp+28h+arg_0]
0x180015661  add     rsp, 20h
0x180015665  pop     rdi
0x180015666  retn
```
