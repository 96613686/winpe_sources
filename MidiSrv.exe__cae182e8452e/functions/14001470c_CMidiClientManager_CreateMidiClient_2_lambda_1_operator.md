# _CMidiClientManager::CreateMidiClient_::_2_::_lambda_1_::operator()

- ea: `0x14001470c`
- end: `0x140014876`
- name: `_CMidiClientManager::CreateMidiClient_::_2_::_lambda_1_::operator()`
- size: `362`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `2`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x140013f70`
- `0x1400152d0`

## callees

- `0x14000c598`
- `0x14001470c`
- `0x140016484`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14001475e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14001477c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14001479b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400147ba`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400147d9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400147f8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140014817`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140014836`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14001475e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14001477c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14001479b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400147ba`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400147d9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400147f8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140014817`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140014836`

## string_xrefs

- `0x14001473c`: `avcore\midi2\service\exe\midiclientmanager.cpp`

## pseudocode

```c
void ***__fastcall CMidiClientManager::CreateMidiClient_::_2_::_lambda_1_::operator()(PSRWLOCK *a1)
{
  unsigned __int64 v2; // rdx
  int v3; // eax
  void *v4; // rcx
  void *v5; // rcx
  void *v6; // rcx
  void *v7; // rcx
  void *v8; // rcx
  void *v9; // rcx
  void *v10; // rcx
  void *v11; // rcx
  void ***result; // rax
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  v2 = *((_QWORD *)(*a1)->Ptr + 9);
  if ( v2 )
  {
    v3 = CMidiClientManager::DestroyMidiClient(a1[1], v2);
    if ( v3 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x428,
        (int)"avcore\\midi2\\service\\exe\\midiclientmanager.cpp",
        (const char *)(unsigned int)v3);
  }
  v4 = *(void **)(*a1)->Ptr;
  if ( v4 )
  {
    CloseHandle(v4);
    *(_QWORD *)(*a1)->Ptr = 0;
  }
  v5 = (void *)*((_QWORD *)(*a1)->Ptr + 1);
  if ( v5 )
  {
    CloseHandle(v5);
    *((_QWORD *)(*a1)->Ptr + 1) = 0;
  }
  v6 = (void *)*((_QWORD *)(*a1)->Ptr + 2);
  if ( v6 )
  {
    CloseHandle(v6);
    *((_QWORD *)(*a1)->Ptr + 2) = 0;
  }
  v7 = (void *)*((_QWORD *)(*a1)->Ptr + 3);
  if ( v7 )
  {
    CloseHandle(v7);
    *((_QWORD *)(*a1)->Ptr + 3) = 0;
  }
  v8 = (void *)*((_QWORD *)(*a1)->Ptr + 4);
  if ( v8 )
  {
    CloseHandle(v8);
    *((_QWORD *)(*a1)->Ptr + 4) = 0;
  }
  v9 = (void *)*((_QWORD *)(*a1)->Ptr + 5);
  if ( v9 )
  {
    CloseHandle(v9);
    *((_QWORD *)(*a1)->Ptr + 5) = 0;
  }
  v10 = (void *)*((_QWORD *)(*a1)->Ptr + 6);
  if ( v10 )
  {
    CloseHandle(v10);
    *((_QWORD *)(*a1)->Ptr + 6) = 0;
  }
  v11 = (void *)*((_QWORD *)(*a1)->Ptr + 7);
  if ( v11 )
  {
    CloseHandle(v11);
    *((_QWORD *)(*a1)->Ptr + 7) = 0;
  }
  *((_DWORD *)(*a1)->Ptr + 16) = 0;
  *((_DWORD *)(*a1)->Ptr + 17) = 0;
  *((_QWORD *)(*a1)->Ptr + 9) = 0;
  result = (void ***)*a1;
  *((_DWORD *)(*a1)->Ptr + 20) = 0;
  return result;
}

```

## disassembly

```asm
0x14001470c  mov     [rsp+arg_0], rbx
0x140014711  push    rdi; int
0x140014712  sub     rsp, 20h
0x140014716  mov     rax, [rcx]
0x140014719  xor     edi, edi
0x14001471b  mov     rbx, rcx
0x14001471e  mov     rdx, [rax]
0x140014721  mov     rdx, [rdx+48h]; unsigned __int64
0x140014725  test    rdx, rdx
0x140014728  jz      short loc_140014750
0x14001472a  mov     rcx, [rcx+8]; SRWLock
0x14001472e  call    ?DestroyMidiClient@CMidiClientManager@@QEAAJ_K@Z; CMidiClientManager::DestroyMidiClient(unsigned __int64)
0x140014733  test    eax, eax
0x140014735  jns     short loc_140014750
0x140014737  mov     rcx, [rsp+28h]; this
0x14001473c  lea     r8, aAvcoreMidi2Ser_1; "avcore\\midi2\\service\\exe\\midiclient"...
0x140014743  mov     r9d, eax; char *
0x140014746  mov     edx, 428h; void *
0x14001474b  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x140014750  mov     rax, [rbx]
0x140014753  mov     rcx, [rax]
0x140014756  mov     rcx, [rcx]; hObject
0x140014759  test    rcx, rcx
0x14001475c  jz      short loc_14001476D
0x14001475e  call    cs:__imp_CloseHandle
0x140014764  mov     rax, [rbx]
0x140014767  mov     rcx, [rax]
0x14001476a  mov     [rcx], rdi
0x14001476d  mov     rax, [rbx]
0x140014770  mov     rcx, [rax]
0x140014773  mov     rcx, [rcx+8]; hObject
0x140014777  test    rcx, rcx
0x14001477a  jz      short loc_14001478C
0x14001477c  call    cs:__imp_CloseHandle
0x140014782  mov     rax, [rbx]
0x140014785  mov     rcx, [rax]
0x140014788  mov     [rcx+8], rdi
0x14001478c  mov     rax, [rbx]
0x14001478f  mov     rcx, [rax]
0x140014792  mov     rcx, [rcx+10h]; hObject
0x140014796  test    rcx, rcx
0x140014799  jz      short loc_1400147AB
0x14001479b  call    cs:__imp_CloseHandle
0x1400147a1  mov     rax, [rbx]
0x1400147a4  mov     rcx, [rax]
0x1400147a7  mov     [rcx+10h], rdi
0x1400147ab  mov     rax, [rbx]
0x1400147ae  mov     rcx, [rax]
0x1400147b1  mov     rcx, [rcx+18h]; hObject
0x1400147b5  test    rcx, rcx
0x1400147b8  jz      short loc_1400147CA
0x1400147ba  call    cs:__imp_CloseHandle
0x1400147c0  mov     rax, [rbx]
0x1400147c3  mov     rcx, [rax]
0x1400147c6  mov     [rcx+18h], rdi
0x1400147ca  mov     rax, [rbx]
0x1400147cd  mov     rcx, [rax]
0x1400147d0  mov     rcx, [rcx+20h]; hObject
0x1400147d4  test    rcx, rcx
0x1400147d7  jz      short loc_1400147E9
0x1400147d9  call    cs:__imp_CloseHandle
0x1400147df  mov     rax, [rbx]
0x1400147e2  mov     rcx, [rax]
0x1400147e5  mov     [rcx+20h], rdi
0x1400147e9  mov     rax, [rbx]
0x1400147ec  mov     rcx, [rax]
0x1400147ef  mov     rcx, [rcx+28h]; hObject
0x1400147f3  test    rcx, rcx
0x1400147f6  jz      short loc_140014808
0x1400147f8  call    cs:__imp_CloseHandle
0x1400147fe  mov     rax, [rbx]
0x140014801  mov     rcx, [rax]
0x140014804  mov     [rcx+28h], rdi
0x140014808  mov     rax, [rbx]
0x14001480b  mov     rcx, [rax]
0x14001480e  mov     rcx, [rcx+30h]; hObject
0x140014812  test    rcx, rcx
0x140014815  jz      short loc_140014827
0x140014817  call    cs:__imp_CloseHandle
0x14001481d  mov     rax, [rbx]
0x140014820  mov     rcx, [rax]
0x140014823  mov     [rcx+30h], rdi
0x140014827  mov     rax, [rbx]
0x14001482a  mov     rcx, [rax]
0x14001482d  mov     rcx, [rcx+38h]; hObject
0x140014831  test    rcx, rcx
0x140014834  jz      short loc_140014846
0x140014836  call    cs:__imp_CloseHandle
0x14001483c  mov     rax, [rbx]
0x14001483f  mov     rcx, [rax]
0x140014842  mov     [rcx+38h], rdi
0x140014846  mov     rax, [rbx]
0x140014849  mov     rcx, [rax]
0x14001484c  mov     [rcx+40h], edi
0x14001484f  mov     rax, [rbx]
0x140014852  mov     rcx, [rax]
0x140014855  mov     [rcx+44h], edi
0x140014858  mov     rax, [rbx]
0x14001485b  mov     rcx, [rax]
0x14001485e  mov     [rcx+48h], rdi
0x140014862  mov     rax, [rbx]
0x140014865  mov     rbx, [rsp+28h+arg_0]
0x14001486a  mov     rcx, [rax]
0x14001486d  mov     [rcx+50h], edi
0x140014870  add     rsp, 20h
0x140014874  pop     rdi
0x140014875  retn
```
