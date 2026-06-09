# CMapi2Handler::ThreadIdle(ulong)

- ea: `0x180012440`
- end: `0x1800124d6`
- name: `?ThreadIdle@CMapi2Handler@@UEAAJK@Z`
- size: `150`
- prototype: `__int64 __fastcall(CMapi2Handler *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting`

## callees

- `0x18000ec50`
- `0x1800113ec`
- `0x18001148c`
- `0x180012440`
- `0x18002f4b0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenMutexW` at `0x18001246a`
- `api-ms-win-core-synch-l1-1-0!OpenMutexW` at `0x18001246a`

## string_xrefs

- `0x1800124a4`: `CMapi2HAndler::ThreadIdle() released MapiManager`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CMapi2Handler::ThreadIdle(CMapi2Handler *this)
{
  struct CMapiManager *v2; // rcx
  unsigned int v3; // ebx
  ATL::CAtlException *v5; // rbx
  ATL::CAtlException *v6; // [rsp+20h] [rbp-18h] BYREF
  HANDLE v7; // [rsp+50h] [rbp+18h] BYREF

  if ( *((_DWORD *)this + 42) && *((_QWORD *)this + 25) )
  {
    v7 = OpenMutexW(0x1F0001u, 0, L"MSSPHTB_Alive");
    if ( !(unsigned int)OutlookSync::IsOutlookAlive((OutlookSync *)&v7) && !*(_QWORD *)(*((_QWORD *)this + 25) + 288LL) )
    {
      try
      {
        CMapiManager::ReleaseMapiManager(v2);
        *((_QWORD *)this + 25) = 0;
        CLogger::Info(L"CMapi2HAndler::ThreadIdle() released MapiManager");
      }
      catch ( ATL::CAtlException *v6 )
      {
        v5 = v6;
        CLogger::Error(*(unsigned int *)v6, L"CMapi2Handler::ThreadIdle threw an exception");
        v3 = *(_DWORD *)v5;
        OutlookSync::~OutlookSync((OutlookSync *)&v7);
        return v3;
      }
      catch ( ... )
      {
        indexer::result::details::result_from_caught_exception<0>();
      }
    }
    OutlookSync::~OutlookSync((OutlookSync *)&v7);
  }
  return 0;
}

```

## disassembly

```asm
0x180012440  push    rbx
0x180012442  sub     rsp, 30h
0x180012446  mov     rbx, rcx
0x180012449  cmp     dword ptr [rcx+0A8h], 0
0x180012450  jz      short loc_1800124CE
0x180012452  cmp     qword ptr [rcx+0C8h], 0
0x18001245a  jz      short loc_1800124CE
0x18001245c  lea     r8, Name; "MSSPHTB_Alive"
0x180012463  xor     edx, edx; bInheritHandle
0x180012465  mov     ecx, 1F0001h; dwDesiredAccess
0x18001246a  call    cs:__imp_OpenMutexW
0x180012470  mov     [rsp+38h+arg_10], rax
0x180012475  lea     rcx, [rsp+38h+arg_10]; this
0x18001247a  call    ?IsOutlookAlive@OutlookSync@@QEAAHXZ; OutlookSync::IsOutlookAlive(void)
0x18001247f  test    eax, eax
0x180012481  jnz     short loc_1800124C4
0x180012483  mov     rax, [rbx+0C8h]
0x18001248a  cmp     qword ptr [rax+120h], 0
0x180012492  jnz     short loc_1800124C4
0x180012494  call    ?ReleaseMapiManager@CMapiManager@@SAJPEAV1@@Z; CMapiManager::ReleaseMapiManager(CMapiManager *)
0x180012499  mov     qword ptr [rbx+0C8h], 0
0x1800124a4  lea     rcx, aCmapi2handlerT_2; "CMapi2HAndler::ThreadIdle() released Ma"...
0x1800124ab  call    ?Info@CLogger@@SAXPEB_WZZ; CLogger::Info(wchar_t const *,...)
0x1800124b0  jmp     short loc_1800124C4
0x1800124b2  mov     ebx, [rsp+38h+arg_0]
0x1800124b6  lea     rcx, [rsp+38h+arg_10]; this
0x1800124bb  call    ??1OutlookSync@@QEAA@XZ; OutlookSync::~OutlookSync(void)
0x1800124c0  mov     eax, ebx
0x1800124c2  jmp     short loc_1800124D0
0x1800124c4  lea     rcx, [rsp+38h+arg_10]; this
0x1800124c9  call    ??1OutlookSync@@QEAA@XZ; OutlookSync::~OutlookSync(void)
0x1800124ce  xor     eax, eax
0x1800124d0  add     rsp, 30h
0x1800124d4  pop     rbx
0x1800124d5  retn
```
