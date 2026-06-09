# CTemplate::Detach(void)

- ea: `0x18001a240`
- end: `0x18001a2ad`
- name: `?Detach@CTemplate@@QEAAJXZ`
- size: `109`
- prototype: `__int64 __fastcall(CTemplate *__hidden this)`
- caller_count: `4`
- callee_count: `4`
- tags: ``

## callers

- `0x180019f44`
- `0x180019fe4`
- `0x180035134`
- `0x18005b7f4`

## callees

- `0x180011800`
- `0x18001a240`
- `0x180031000`
- `0x180064010`

## import_xrefs

- `KERNEL32!HeapFree` at `0x18002f677`
- `KERNEL32!HeapFree` at `0x18002f677`
- `KERNEL32!LeaveCriticalSection` at `0x18001a286`
- `KERNEL32!LeaveCriticalSection` at `0x18001a286`
- `KERNEL32!GetCurrentThreadId` at `0x18002f60b`
- `KERNEL32!GetCurrentThreadId` at `0x18002f60b`
- `KERNEL32!EnterCriticalSection` at `0x18001a25c`
- `KERNEL32!EnterCriticalSection` at `0x18001a25c`

## pseudocode

```c
__int64 __fastcall CTemplate::Detach(CTemplate *this)
{
  CTemplate *v2; // rcx
  CApplnMgr *v4; // rcx
  BOOL v5; // ebp
  __int64 i; // rdi
  __int64 v7; // rax
  __int64 v8; // rsi

  if ( (*((_BYTE *)this + 392) & 0x10) != 0 )
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 208));
  while ( 1 )
  {
    v2 = (CTemplate *)*((_QWORD *)this + 32);
    if ( (CTemplate *)((char *)this + 248) == v2 )
      break;
    if ( v2 )
      (**(void (__fastcall ***)(CTemplate *, __int64))v2)(v2, 1);
  }
  if ( (*((_BYTE *)this + 392) & 0x10) != 0 )
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 208));
  if ( *((_QWORD *)this + 23) )
  {
    v5 = GetCurrentThreadId() == g_dwDebugThreadId;
    for ( i = 0; (unsigned int)i < *((_DWORD *)this + 44); i = (unsigned int)(i + 1) )
    {
      v7 = *((_QWORD *)this + 23);
      v8 = *(_QWORD *)(v7 + 8 * i);
      if ( v8 )
      {
        if ( v5 )
        {
          CActiveScriptEngine::FinalRelease(*(CActiveScriptEngine **)(v7 + 8 * i));
        }
        else
        {
          CApplnMgr::AddEngine(v4, *(struct CActiveScriptEngine **)(v7 + 8 * i));
          (*(void (__fastcall **)(__int64))(*(_QWORD *)(v8 + 8) + 16LL))(v8 + 8);
        }
      }
    }
    HeapFree(g_hDenaliHeap, 0, *((LPVOID *)this + 23));
    *((_QWORD *)this + 23) = 0;
  }
  *((_DWORD *)this + 98) &= ~0x100u;
  return 0;
}

```

## disassembly

```asm
0x18001a240  push    rbx
0x18001a242  push    rbp
0x18001a243  push    rsi
0x18001a244  push    rdi
0x18001a245  sub     rsp, 28h
0x18001a249  test    byte ptr [rcx+188h], 10h
0x18001a250  mov     rbx, rcx
0x18001a253  jz      short loc_18001A262
0x18001a255  add     rcx, 0D0h; lpCriticalSection
0x18001a25c  call    cs:__imp_EnterCriticalSection
0x18001a262  lea     rdi, [rbx+0F8h]
0x18001a269  mov     rcx, [rdi+8]
0x18001a26d  cmp     rdi, rcx
0x18001a270  jnz     loc_18002F5EC
0x18001a276  test    byte ptr [rbx+188h], 10h
0x18001a27d  jz      short loc_18001A28C
0x18001a27f  lea     rcx, [rbx+0D0h]; lpCriticalSection
0x18001a286  call    cs:__imp_LeaveCriticalSection
0x18001a28c  cmp     qword ptr [rbx+0B8h], 0
0x18001a294  jnz     loc_18002F60B
0x18001a29a  btr     dword ptr [rbx+188h], 8
0x18001a2a2  xor     eax, eax
0x18001a2a4  add     rsp, 28h
0x18001a2a8  pop     rdi
0x18001a2a9  pop     rsi
0x18001a2aa  pop     rbp
0x18001a2ab  pop     rbx
0x18001a2ac  retn
0x18002f5ec  test    rcx, rcx
0x18002f5ef  jz      loc_18001A269
0x18002f5f5  mov     rax, [rcx]
0x18002f5f8  mov     edx, 1
0x18002f5fd  mov     rax, [rax]
0x18002f600  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f605  nop
0x18002f606  jmp     loc_18001A269
0x18002f60b  call    cs:__imp_GetCurrentThreadId
0x18002f611  xor     ebp, ebp
0x18002f613  cmp     eax, cs:?g_dwDebugThreadId@@3KA; ulong g_dwDebugThreadId
0x18002f619  setz    bpl
0x18002f61d  xor     edi, edi
0x18002f61f  cmp     [rbx+0B0h], edi
0x18002f625  jbe     short loc_18002F667
0x18002f627  mov     rax, [rbx+0B8h]
0x18002f62e  mov     rsi, [rax+rdi*8]
0x18002f632  test    rsi, rsi
0x18002f635  jz      short loc_18002F65D
0x18002f637  test    ebp, ebp
0x18002f639  jz      short loc_18002F645
0x18002f63b  mov     rcx, rsi; this
0x18002f63e  call    ?FinalRelease@CActiveScriptEngine@@QEAAKXZ; CActiveScriptEngine::FinalRelease(void)
0x18002f643  jmp     short loc_18002F65D
0x18002f645  mov     rdx, rsi; struct CActiveScriptEngine *
0x18002f648  call    ?AddEngine@CApplnMgr@@QEAAJPEAVCActiveScriptEngine@@@Z; CApplnMgr::AddEngine(CActiveScriptEngine *)
0x18002f64d  lea     rcx, [rsi+8]
0x18002f651  mov     rax, [rcx]
0x18002f654  mov     rax, [rax+10h]
0x18002f658  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f65d  inc     edi
0x18002f65f  cmp     edi, [rbx+0B0h]
0x18002f665  jb      short loc_18002F627
0x18002f667  mov     r8, [rbx+0B8h]; lpMem
0x18002f66e  xor     edx, edx; dwFlags
0x18002f670  mov     rcx, cs:?g_hDenaliHeap@@3PEAXEA; hHeap
0x18002f677  call    cs:__imp_HeapFree
0x18002f67d  mov     qword ptr [rbx+0B8h], 0
0x18002f688  jmp     loc_18001A29A
```
