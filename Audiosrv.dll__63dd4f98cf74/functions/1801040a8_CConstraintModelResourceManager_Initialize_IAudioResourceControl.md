# CConstraintModelResourceManager::Initialize(IAudioResourceControl *)

- ea: `0x1801040a8`
- end: `0x1801041e2`
- name: `?Initialize@CConstraintModelResourceManager@@AEAAJPEAUIAudioResourceControl@@@Z`
- size: `314`
- prototype: `__int64 __fastcall(CConstraintModelResourceManager *__hidden this, struct IAudioResourceControl *)`
- caller_count: `1`
- callee_count: `5`
- tags: `installer_update`

## callers

- `0x1801038c8`

## callees

- `0x180032600`
- `0x1800b5ee0`
- `0x1800c4430`
- `0x1801040a8`
- `0x180159870`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x1801041c6`
- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x1801041c6`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1801040d2`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18010411a`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1801040d2`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18010411a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801040e9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180104132`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801040e9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180104132`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x18010418f`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x18010418f`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x1801041b5`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x1801041b5`

## pseudocode

```c
__int64 __fastcall CConstraintModelResourceManager::Initialize(
        CConstraintModelResourceManager *this,
        struct IAudioResourceControl *a2)
{
  bool v2; // zf
  signed int v4; // edx
  char *EventW; // rax
  signed int LastError; // eax
  HANDLE v7; // rax
  signed int v8; // eax
  CConstraintModel *v9; // rax
  struct _TP_WAIT *ThreadpoolWait; // rax

  v2 = *((_QWORD *)this + 8) == 0;
  *((_QWORD *)this + 21) = a2;
  if ( v2 || (v4 = 0, *((_QWORD *)this + 8) == -1) )
  {
    EventW = (char *)CreateEventW(0, 0, 0, 0);
    *((_QWORD *)this + 8) = EventW;
    if ( (unsigned __int64)(EventW - 1) > 0xFFFFFFFFFFFFFFFDuLL )
    {
      LastError = GetLastError();
      v4 = LastError;
      if ( LastError > 0 )
        v4 = (unsigned __int16)LastError | 0x80070000;
    }
    else
    {
      v4 = 0;
    }
  }
  if ( ((*((_QWORD *)this + 23) + 1LL) & 0xFFFFFFFFFFFFFFFEuLL) != 0 )
  {
LABEL_11:
    if ( v4 < 0 )
      return (unsigned int)v4;
    goto LABEL_12;
  }
  v7 = CreateEventW(0, 0, 0, 0);
  *((_QWORD *)this + 23) = v7;
  if ( (((unsigned __int64)v7 + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
  {
    v8 = GetLastError();
    v4 = v8;
    if ( v8 > 0 )
      v4 = (unsigned __int16)v8 | 0x80070000;
    goto LABEL_11;
  }
LABEL_12:
  v9 = (CConstraintModel *)operator new(0xF0u);
  if ( v9 )
    v9 = CConstraintModel::CConstraintModel(v9);
  *((_QWORD *)this + 7) = v9;
  if ( !v9 )
    return (unsigned int)-2147024882;
  v4 = CConstraintModel::Initialize(v9);
  if ( v4 >= 0 )
  {
    ThreadpoolWait = CreateThreadpoolWait(CConstraintModelResourceManager::s_WorkerThreadProc, this, 0);
    *((_QWORD *)this + 22) = ThreadpoolWait;
    if ( ThreadpoolWait )
    {
      SetThreadpoolWait(ThreadpoolWait, *((HANDLE *)this + 23), 0);
      *((_QWORD *)this + 9) = CreateMutexW(0, 0, L"Global\\AudioResourceAcquisitionMutex");
      return (unsigned int)CConstraintModelResourceManager::SetupKeywordDetectorPriority(this);
    }
    return (unsigned int)-2147024882;
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x1801040a8  push    rbx
0x1801040aa  sub     rsp, 20h
0x1801040ae  cmp     qword ptr [rcx+40h], 0
0x1801040b3  mov     rbx, rcx
0x1801040b6  mov     [rcx+0A8h], rdx
0x1801040bd  jz      short loc_1801040C8
0x1801040bf  xor     edx, edx
0x1801040c1  cmp     qword ptr [rcx+40h], 0FFFFFFFFFFFFFFFFh
0x1801040c6  jnz     short loc_1801040FE
0x1801040c8  xor     r9d, r9d; lpName
0x1801040cb  xor     r8d, r8d; bInitialState
0x1801040ce  xor     edx, edx; bManualReset
0x1801040d0  xor     ecx, ecx; lpEventAttributes
0x1801040d2  call    cs:__imp_CreateEventW
0x1801040d8  mov     [rbx+40h], rax
0x1801040dc  dec     rax
0x1801040df  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1801040e3  ja      short loc_1801040E9
0x1801040e5  xor     edx, edx
0x1801040e7  jmp     short loc_1801040FE
0x1801040e9  call    cs:__imp_GetLastError
0x1801040ef  mov     edx, eax
0x1801040f1  test    eax, eax
0x1801040f3  jle     short loc_1801040FE
0x1801040f5  movzx   edx, ax
0x1801040f8  or      edx, 80070000h
0x1801040fe  mov     rax, [rbx+0B8h]
0x180104105  inc     rax
0x180104108  test    rax, 0FFFFFFFFFFFFFFFEh
0x18010410e  jnz     short loc_180104147
0x180104110  xor     r9d, r9d; lpName
0x180104113  xor     r8d, r8d; bInitialState
0x180104116  xor     edx, edx; bManualReset
0x180104118  xor     ecx, ecx; lpEventAttributes
0x18010411a  call    cs:__imp_CreateEventW
0x180104120  mov     [rbx+0B8h], rax
0x180104127  inc     rax
0x18010412a  test    rax, 0FFFFFFFFFFFFFFFEh
0x180104130  jnz     short loc_18010414F
0x180104132  call    cs:__imp_GetLastError
0x180104138  mov     edx, eax
0x18010413a  test    eax, eax
0x18010413c  jle     short loc_180104147
0x18010413e  movzx   edx, ax
0x180104141  or      edx, 80070000h
0x180104147  test    edx, edx
0x180104149  js      loc_1801041DA
0x18010414f  mov     ecx, 0F0h; unsigned __int64
0x180104154  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180104159  mov     [rsp+28h+arg_0], rax
0x18010415e  test    rax, rax
0x180104161  jz      short loc_18010416B
0x180104163  mov     rcx, rax; this
0x180104166  call    ??0CConstraintModel@@QEAA@XZ; CConstraintModel::CConstraintModel(void)
0x18010416b  mov     [rbx+38h], rax
0x18010416f  test    rax, rax
0x180104172  jz      short loc_1801041A1
0x180104174  mov     rcx, rax; this
0x180104177  call    ?Initialize@CConstraintModel@@QEAAJXZ; CConstraintModel::Initialize(void)
0x18010417c  mov     edx, eax
0x18010417e  test    eax, eax
0x180104180  js      short loc_1801041DA
0x180104182  xor     r8d, r8d; pcbe
0x180104185  lea     rcx, ?s_WorkerThreadProc@CConstraintModelResourceManager@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WAIT@@J@Z; pfnwa
0x18010418c  mov     rdx, rbx; pv
0x18010418f  call    cs:__imp_CreateThreadpoolWait
0x180104195  mov     [rbx+0B0h], rax
0x18010419c  test    rax, rax
0x18010419f  jnz     short loc_1801041A8
0x1801041a1  mov     edx, 8007000Eh
0x1801041a6  jmp     short loc_1801041DA
0x1801041a8  mov     rdx, [rbx+0B8h]; h
0x1801041af  xor     r8d, r8d; pftTimeout
0x1801041b2  mov     rcx, rax; pwa
0x1801041b5  call    cs:__imp_SetThreadpoolWait
0x1801041bb  lea     r8, aGlobalAudiores; "Global\\AudioResourceAcquisitionMutex"
0x1801041c2  xor     edx, edx; bInitialOwner
0x1801041c4  xor     ecx, ecx; lpMutexAttributes
0x1801041c6  call    cs:__imp_CreateMutexW
0x1801041cc  mov     rcx, rbx; this
0x1801041cf  mov     [rbx+48h], rax
0x1801041d3  call    ?SetupKeywordDetectorPriority@CConstraintModelResourceManager@@AEAAJXZ; CConstraintModelResourceManager::SetupKeywordDetectorPriority(void)
0x1801041d8  mov     edx, eax
0x1801041da  mov     eax, edx
0x1801041dc  add     rsp, 20h
0x1801041e0  pop     rbx
0x1801041e1  retn
```
