# CConstraintModelResourceManager::Initialize(IAudioResourceControl *)

- ea: `0x180103e18`
- end: `0x180103f52`
- name: `?Initialize@CConstraintModelResourceManager@@AEAAJPEAUIAudioResourceControl@@@Z`
- size: `314`
- prototype: `__int64 __fastcall(CConstraintModelResourceManager *__hidden this, struct IAudioResourceControl *)`
- caller_count: `1`
- callee_count: `5`
- tags: `installer_update`

## callers

- `0x180103638`

## callees

- `0x1800324a0`
- `0x1800b7a30`
- `0x1800c62c0`
- `0x180103e18`
- `0x180158b60`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x180103f36`
- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x180103f36`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180103e42`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180103e8a`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180103e42`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180103e8a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180103e59`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180103ea2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180103e59`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180103ea2`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x180103eff`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x180103eff`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x180103f25`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x180103f25`

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
0x180103e18  push    rbx
0x180103e1a  sub     rsp, 20h
0x180103e1e  cmp     qword ptr [rcx+40h], 0
0x180103e23  mov     rbx, rcx
0x180103e26  mov     [rcx+0A8h], rdx
0x180103e2d  jz      short loc_180103E38
0x180103e2f  xor     edx, edx
0x180103e31  cmp     qword ptr [rcx+40h], 0FFFFFFFFFFFFFFFFh
0x180103e36  jnz     short loc_180103E6E
0x180103e38  xor     r9d, r9d; lpName
0x180103e3b  xor     r8d, r8d; bInitialState
0x180103e3e  xor     edx, edx; bManualReset
0x180103e40  xor     ecx, ecx; lpEventAttributes
0x180103e42  call    cs:__imp_CreateEventW
0x180103e48  mov     [rbx+40h], rax
0x180103e4c  dec     rax
0x180103e4f  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180103e53  ja      short loc_180103E59
0x180103e55  xor     edx, edx
0x180103e57  jmp     short loc_180103E6E
0x180103e59  call    cs:__imp_GetLastError
0x180103e5f  mov     edx, eax
0x180103e61  test    eax, eax
0x180103e63  jle     short loc_180103E6E
0x180103e65  movzx   edx, ax
0x180103e68  or      edx, 80070000h
0x180103e6e  mov     rax, [rbx+0B8h]
0x180103e75  inc     rax
0x180103e78  test    rax, 0FFFFFFFFFFFFFFFEh
0x180103e7e  jnz     short loc_180103EB7
0x180103e80  xor     r9d, r9d; lpName
0x180103e83  xor     r8d, r8d; bInitialState
0x180103e86  xor     edx, edx; bManualReset
0x180103e88  xor     ecx, ecx; lpEventAttributes
0x180103e8a  call    cs:__imp_CreateEventW
0x180103e90  mov     [rbx+0B8h], rax
0x180103e97  inc     rax
0x180103e9a  test    rax, 0FFFFFFFFFFFFFFFEh
0x180103ea0  jnz     short loc_180103EBF
0x180103ea2  call    cs:__imp_GetLastError
0x180103ea8  mov     edx, eax
0x180103eaa  test    eax, eax
0x180103eac  jle     short loc_180103EB7
0x180103eae  movzx   edx, ax
0x180103eb1  or      edx, 80070000h
0x180103eb7  test    edx, edx
0x180103eb9  js      loc_180103F4A
0x180103ebf  mov     ecx, 0F0h; unsigned __int64
0x180103ec4  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180103ec9  mov     [rsp+28h+arg_0], rax
0x180103ece  test    rax, rax
0x180103ed1  jz      short loc_180103EDB
0x180103ed3  mov     rcx, rax; this
0x180103ed6  call    ??0CConstraintModel@@QEAA@XZ; CConstraintModel::CConstraintModel(void)
0x180103edb  mov     [rbx+38h], rax
0x180103edf  test    rax, rax
0x180103ee2  jz      short loc_180103F11
0x180103ee4  mov     rcx, rax; this
0x180103ee7  call    ?Initialize@CConstraintModel@@QEAAJXZ; CConstraintModel::Initialize(void)
0x180103eec  mov     edx, eax
0x180103eee  test    eax, eax
0x180103ef0  js      short loc_180103F4A
0x180103ef2  xor     r8d, r8d; pcbe
0x180103ef5  lea     rcx, ?s_WorkerThreadProc@CConstraintModelResourceManager@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WAIT@@J@Z; pfnwa
0x180103efc  mov     rdx, rbx; pv
0x180103eff  call    cs:__imp_CreateThreadpoolWait
0x180103f05  mov     [rbx+0B0h], rax
0x180103f0c  test    rax, rax
0x180103f0f  jnz     short loc_180103F18
0x180103f11  mov     edx, 8007000Eh
0x180103f16  jmp     short loc_180103F4A
0x180103f18  mov     rdx, [rbx+0B8h]; h
0x180103f1f  xor     r8d, r8d; pftTimeout
0x180103f22  mov     rcx, rax; pwa
0x180103f25  call    cs:__imp_SetThreadpoolWait
0x180103f2b  lea     r8, aGlobalAudiores; "Global\\AudioResourceAcquisitionMutex"
0x180103f32  xor     edx, edx; bInitialOwner
0x180103f34  xor     ecx, ecx; lpMutexAttributes
0x180103f36  call    cs:__imp_CreateMutexW
0x180103f3c  mov     rcx, rbx; this
0x180103f3f  mov     [rbx+48h], rax
0x180103f43  call    ?SetupKeywordDetectorPriority@CConstraintModelResourceManager@@AEAAJXZ; CConstraintModelResourceManager::SetupKeywordDetectorPriority(void)
0x180103f48  mov     edx, eax
0x180103f4a  mov     eax, edx
0x180103f4c  add     rsp, 20h
0x180103f50  pop     rbx
0x180103f51  retn
```
