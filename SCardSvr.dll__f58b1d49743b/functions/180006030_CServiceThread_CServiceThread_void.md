# CServiceThread::~CServiceThread(void)

- ea: `0x180006030`
- end: `0x1800062db`
- name: `??1CServiceThread@@QEAA@XZ`
- size: `683`
- prototype: `void __fastcall(CServiceThread *__hidden this)`
- caller_count: `3`
- callee_count: `7`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x180006004`
- `0x1800063c0`
- `0x18000dca0`

## callees

- `0x180003860`
- `0x180006030`
- `0x180009150`
- `0x1800106f0`
- `0x180014180`
- `0x180023168`
- `0x180037010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000610a`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000622f`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000610a`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000622f`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000616e`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000616e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000608b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000608b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000607d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000607d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800061d9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000628f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800061d9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000628f`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x1800060a2`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x1800060b8`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x1800060a2`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x1800060b8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006246`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006280`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000629a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006246`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006280`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000629a`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CServiceThread::~CServiceThread(CServiceThread *this)
{
  CServiceThread *v1; // rdi
  unsigned int v2; // ebx
  char *v3; // rcx
  void *v4; // rbx
  HANDLE ProcessHeap; // rax
  char *v6; // rcx
  void *v7; // rcx
  char *v8; // rsi
  __int64 v9; // rdx
  struct CReaderReference *v10; // [rsp+20h] [rbp-38h] BYREF
  unsigned int v12; // [rsp+70h] [rbp+18h] BYREF
  char *v13; // [rsp+78h] [rbp+20h]

  v1 = this;
  v2 = *((_DWORD *)this + 15);
  while ( v2 )
  {
    --v2;
    v8 = (char *)v1 + 48;
    v13 = (char *)v1 + 48;
    if ( *((_DWORD *)v1 + 15) > v2 )
    {
      v9 = *(_QWORD *)(*((_QWORD *)v1 + 8) + 8LL * (int)v2);
      v10 = (struct CReaderReference *)v9;
      if ( v9 )
      {
        try
        {
          CReaderProxy::Disconnect(*(CReaderProxy **)v9, (struct CReader::ActiveState *)(v9 + 8), 1u, &v12);
        }
        catch ( ... )
        {
          v1 = this;
          v8 = v13;
        }
        CDynamicArray<CReaderReference>::Set(v8, v2, 0);
        CalaisReleaseReader(&v10);
      }
    }
  }
  if ( (unsigned __int64)(*(_QWORD *)v1 - 1LL) <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    SetEvent(*(HANDLE *)v1);
    if ( (unsigned __int64)(*(_QWORD *)v1 - 1LL) <= 0xFFFFFFFFFFFFFFFDuLL )
    {
      CloseHandle(*(HANDLE *)v1);
      *(_QWORD *)v1 = 0;
    }
  }
  v3 = (char *)*((_QWORD *)v1 + 2);
  if ( (unsigned __int64)(v3 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    CloseHandle(v3);
    *((_QWORD *)v1 + 2) = 0;
  }
  v4 = (void *)*((_QWORD *)v1 + 22);
  if ( v4 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v4);
    *((_QWORD *)v1 + 22) = 0;
  }
  if ( !TlsSetValue(dwTlsIndex, *((LPVOID *)v1 + 9)) || !TlsSetValue(dword_18004B240, 0) )
    GetLastError();
  if ( !(*(unsigned int (__fastcall **)(__int64))(*((_QWORD *)v1 + 10) + 16LL))((__int64)v1 + 80) )
  {
    (**((void (__fastcall ***)(__int64, _QWORD, _QWORD))v1 + 10))((__int64)v1 + 80, 0, 0);
    ++*((_DWORD *)v1 + 37);
    *((_QWORD *)v1 + 17) = 0;
    *((_DWORD *)v1 + 36) = 0;
    if ( !SetEvent(*((HANDLE *)v1 + 19)) )
      GetLastError();
    (*(void (__fastcall **)(__int64))(*((_QWORD *)v1 + 10) + 8LL))((__int64)v1 + 80);
    v6 = (char *)*((_QWORD *)v1 + 19);
    if ( (unsigned __int64)(v6 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    {
      CloseHandle(v6);
      *((_QWORD *)v1 + 19) = 0;
    }
  }
  if ( (unsigned __int64)(*((_QWORD *)v1 + 19) - 1LL) <= 0xFFFFFFFFFFFFFFFDuLL )
    CHandleObject::Close((CServiceThread *)((char *)v1 + 152));
  *((_QWORD *)v1 + 10) = &CCriticalSectionObject::`vftable';
  if ( !*((_DWORD *)v1 + 32) )
    DeleteCriticalSection((LPCRITICAL_SECTION)((char *)v1 + 88));
  *((_QWORD *)v1 + 6) = &CDynamicArray<CServiceThread>::`vftable';
  v7 = (void *)*((_QWORD *)v1 + 8);
  if ( v7 )
  {
    operator delete[](v7);
    *((_QWORD *)v1 + 8) = 0;
    *((_QWORD *)v1 + 7) = 0;
  }
  if ( (unsigned __int64)(*((_QWORD *)v1 + 4) - 1LL) <= 0xFFFFFFFFFFFFFFFDuLL )
    CHandleObject::Close((CServiceThread *)((char *)v1 + 32));
  if ( (unsigned __int64)(*((_QWORD *)v1 + 2) - 1LL) <= 0xFFFFFFFFFFFFFFFDuLL )
    CHandleObject::Close((CServiceThread *)((char *)v1 + 16));
  if ( (unsigned __int64)(*(_QWORD *)v1 - 1LL) <= 0xFFFFFFFFFFFFFFFDuLL )
    CHandleObject::Close(v1);
}

```

## disassembly

```asm
0x180006030  mov     [rsp+arg_0], rcx
0x180006035  push    rbx
0x180006036  push    rsi
0x180006037  push    rdi
0x180006038  push    r14
0x18000603a  sub     rsp, 38h
0x18000603e  mov     rdi, rcx
0x180006041  mov     ebx, [rcx+3Ch]
0x180006044  test    ebx, ebx
0x180006046  jnz     loc_1800061E4
0x18000604c  mov     rcx, [rdi]; hEvent
0x18000604f  lea     rax, [rcx-1]
0x180006053  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180006057  jbe     loc_18000622F
0x18000605d  xor     esi, esi
0x18000605f  mov     rcx, [rdi+10h]; hObject
0x180006063  lea     rax, [rcx-1]
0x180006067  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18000606b  jbe     loc_180006280
0x180006071  mov     rbx, [rdi+0B0h]
0x180006078  test    rbx, rbx
0x18000607b  jz      short loc_180006098
0x18000607d  call    cs:__imp_GetProcessHeap
0x180006083  mov     r8, rbx; lpMem
0x180006086  xor     edx, edx; dwFlags
0x180006088  mov     rcx, rax; hHeap
0x18000608b  call    cs:__imp_HeapFree
0x180006091  mov     [rdi+0B0h], rsi
0x180006098  mov     rdx, [rdi+48h]; lpTlsValue
0x18000609c  mov     ecx, cs:dwTlsIndex; dwTlsIndex
0x1800060a2  call    cs:__imp_TlsSetValue
0x1800060a8  test    eax, eax
0x1800060aa  jz      loc_1800061D9
0x1800060b0  xor     edx, edx; lpTlsValue
0x1800060b2  mov     ecx, cs:dword_18004B240; dwTlsIndex
0x1800060b8  call    cs:__imp_TlsSetValue
0x1800060be  test    eax, eax
0x1800060c0  jz      loc_1800061D9
0x1800060c6  mov     rax, [rdi+50h]
0x1800060ca  lea     rcx, [rdi+50h]
0x1800060ce  mov     rax, [rax+10h]
0x1800060d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800060d7  test    eax, eax
0x1800060d9  jnz     short loc_18000613F
0x1800060db  mov     rax, [rdi+50h]
0x1800060df  xor     r8d, r8d
0x1800060e2  xor     edx, edx
0x1800060e4  lea     rcx, [rdi+50h]
0x1800060e8  mov     rax, [rax]
0x1800060eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800060f0  inc     dword ptr [rdi+94h]
0x1800060f6  mov     [rdi+88h], rsi
0x1800060fd  mov     [rdi+90h], esi
0x180006103  mov     rcx, [rdi+98h]; hEvent
0x18000610a  call    cs:__imp_SetEvent
0x180006110  test    eax, eax
0x180006112  jz      loc_18000628F
0x180006118  mov     rax, [rdi+50h]
0x18000611c  lea     rcx, [rdi+50h]
0x180006120  mov     rax, [rax+8]
0x180006124  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006129  nop
0x18000612a  mov     rcx, [rdi+98h]; hObject
0x180006131  lea     rax, [rcx-1]
0x180006135  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180006139  jbe     loc_18000629A
0x18000613f  lea     rcx, [rdi+98h]; this
0x180006146  mov     rax, [rcx]
0x180006149  dec     rax
0x18000614c  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180006150  jbe     loc_1800062AC
0x180006156  lea     rax, ??_7CCriticalSectionObject@@6B@; const CCriticalSectionObject::`vftable'
0x18000615d  mov     [rdi+50h], rax
0x180006161  cmp     dword ptr [rdi+80h], 0
0x180006168  jnz     short loc_180006175
0x18000616a  lea     rcx, [rdi+58h]; lpCriticalSection
0x18000616e  call    cs:__imp_DeleteCriticalSection
0x180006174  nop
0x180006175  lea     rax, ??_7?$CDynamicArray@VCServiceThread@@@@6B@; const CDynamicArray<CServiceThread>::`vftable'
0x18000617c  mov     [rdi+30h], rax
0x180006180  mov     rcx, [rdi+40h]; Block
0x180006184  test    rcx, rcx
0x180006187  jz      short loc_18000619A
0x180006189  call    ??_V@YAXPEAX@Z; operator delete[](void *)
0x18000618e  mov     [rdi+40h], rsi
0x180006192  mov     qword ptr [rdi+38h], 0
0x18000619a  lea     rcx, [rdi+20h]; this
0x18000619e  mov     rax, [rcx]
0x1800061a1  dec     rax
0x1800061a4  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800061a8  jbe     loc_1800062B6
0x1800061ae  mov     rax, [rdi+10h]
0x1800061b2  dec     rax
0x1800061b5  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800061b9  jbe     loc_1800062C0
0x1800061bf  mov     rax, [rdi]
0x1800061c2  dec     rax
0x1800061c5  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800061c9  jbe     loc_1800062CE
0x1800061cf  add     rsp, 38h
0x1800061d3  pop     r14
0x1800061d5  pop     rdi
0x1800061d6  pop     rsi
0x1800061d7  pop     rbx
0x1800061d8  retn
0x1800061d9  call    cs:__imp_GetLastError
0x1800061df  jmp     loc_1800060C6
0x1800061e4  dec     ebx
0x1800061e6  mov     [rsp+58h+arg_8], ebx
0x1800061ea  lea     rsi, [rdi+30h]
0x1800061ee  mov     [rsp+58h+arg_18], rsi
0x1800061f3  cmp     [rsi+0Ch], ebx
0x1800061f6  jbe     loc_180006044
0x1800061fc  movsxd  rcx, ebx
0x1800061ff  mov     rax, [rsi+10h]
0x180006203  mov     rdx, [rax+rcx*8]
0x180006207  mov     [rsp+58h+var_38], rdx
0x18000620c  test    rdx, rdx
0x18000620f  jz      loc_180006044
0x180006215  mov     rcx, [rdx]; this
0x180006218  add     rdx, 8; struct CReader::ActiveState *
0x18000621c  lea     r9, [rsp+58h+arg_10]; unsigned int *
0x180006221  mov     r8d, 1; unsigned int
0x180006227  call    ?Disconnect@CReaderProxy@@QEAAXPEAUActiveState@CReader@@KPEAK@Z; CReaderProxy::Disconnect(CReader::ActiveState *,ulong,ulong *)
0x18000622c  nop
0x18000622d  jmp     short loc_180006264
0x18000622f  call    cs:__imp_SetEvent
0x180006235  mov     rcx, [rdi]; hObject
0x180006238  lea     rax, [rcx-1]
0x18000623c  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180006240  ja      loc_18000605D
0x180006246  call    cs:__imp_CloseHandle
0x18000624c  xor     esi, esi
0x18000624e  mov     [rdi], rsi
0x180006251  jmp     loc_18000605F
0x180006256  mov     rdi, [rsp+58h+arg_0]
0x18000625b  mov     ebx, [rsp+58h+arg_8]
0x18000625f  mov     rsi, [rsp+58h+arg_18]
0x180006264  xor     r8d, r8d
0x180006267  mov     edx, ebx
0x180006269  mov     rcx, rsi
0x18000626c  call    ?Set@?$CDynamicArray@VCReaderReference@@@@QEAAPEAVCReaderReference@@HPEAV2@@Z; CDynamicArray<CReaderReference>::Set(int,CReaderReference *)
0x180006271  lea     rcx, [rsp+58h+var_38]; struct CReaderReference **
0x180006276  call    ?CalaisReleaseReader@@YAXPEAPEAVCReaderReference@@@Z; CalaisReleaseReader(CReaderReference * *)
0x18000627b  jmp     loc_180006044
0x180006280  call    cs:__imp_CloseHandle
0x180006286  mov     [rdi+10h], rsi
0x18000628a  jmp     loc_180006071
0x18000628f  call    cs:__imp_GetLastError
0x180006295  jmp     loc_180006118
0x18000629a  call    cs:__imp_CloseHandle
0x1800062a0  mov     [rdi+98h], rsi
0x1800062a7  jmp     loc_18000613F
0x1800062ac  call    ?Close@CHandleObject@@QEAAKXZ; CHandleObject::Close(void)
0x1800062b1  jmp     loc_180006156
0x1800062b6  call    ?Close@CHandleObject@@QEAAKXZ; CHandleObject::Close(void)
0x1800062bb  jmp     loc_1800061AE
0x1800062c0  lea     rcx, [rdi+10h]; this
0x1800062c4  call    ?Close@CHandleObject@@QEAAKXZ; CHandleObject::Close(void)
0x1800062c9  jmp     loc_1800061BF
0x1800062ce  mov     rcx, rdi; this
0x1800062d1  call    ?Close@CHandleObject@@QEAAKXZ; CHandleObject::Close(void)
0x1800062d6  jmp     loc_1800061CF
```
