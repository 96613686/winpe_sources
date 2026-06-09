# CMutex::~CMutex(void)

- ea: `0x180013fc0`
- end: `0x180014079`
- name: `??1CMutex@@QEAA@XZ`
- size: `185`
- prototype: `void __fastcall(CMutex *__hidden this)`
- caller_count: `4`
- callee_count: `3`
- tags: ``

## callers

- `0x1800179b0`
- `0x180033490`
- `0x180035f00`
- `0x180035f19`

## callees

- `0x180013fc0`
- `0x180014180`
- `0x180037010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180014000`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180014000`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001404c`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001404c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001405e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001405e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180014066`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180014066`

## pseudocode

```c
void __fastcall CMutex::~CMutex(CMutex *this)
{
  char *v2; // rcx

  if ( !(*(unsigned int (__fastcall **)(CMutex *))(*(_QWORD *)this + 16LL))(this) )
  {
    (**(void (__fastcall ***)(CMutex *, _QWORD, _QWORD))this)(this, 0, 0);
    ++*((_DWORD *)this + 17);
    *((_QWORD *)this + 7) = 0;
    *((_DWORD *)this + 16) = 0;
    if ( !SetEvent(*((HANDLE *)this + 9)) )
      GetLastError();
    (*(void (__fastcall **)(CMutex *))(*(_QWORD *)this + 8LL))(this);
    v2 = (char *)*((_QWORD *)this + 9);
    if ( (unsigned __int64)(v2 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    {
      CloseHandle(v2);
      *((_QWORD *)this + 9) = 0;
    }
  }
  if ( (unsigned __int64)(*((_QWORD *)this + 9) - 1LL) <= 0xFFFFFFFFFFFFFFFDuLL )
    CHandleObject::Close((CMutex *)((char *)this + 72));
  *(_QWORD *)this = &CCriticalSectionObject::`vftable';
  if ( !*((_DWORD *)this + 12) )
    DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
}

```

## disassembly

```asm
0x180013fc0  mov     [rsp+arg_0], rbx
0x180013fc5  push    rdi
0x180013fc6  sub     rsp, 20h
0x180013fca  mov     rbx, rcx
0x180013fcd  mov     rax, [rcx]
0x180013fd0  mov     rax, [rax+10h]
0x180013fd4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013fd9  test    eax, eax
0x180013fdb  jnz     short loc_180014028
0x180013fdd  mov     rax, [rbx]
0x180013fe0  xor     r8d, r8d
0x180013fe3  xor     edx, edx
0x180013fe5  mov     rcx, rbx
0x180013fe8  mov     rax, [rax]
0x180013feb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013ff0  inc     dword ptr [rbx+44h]
0x180013ff3  xor     edi, edi
0x180013ff5  mov     [rbx+38h], rdi
0x180013ff9  mov     [rbx+40h], edi
0x180013ffc  mov     rcx, [rbx+48h]; hEvent
0x180014000  call    cs:__imp_SetEvent
0x180014006  test    eax, eax
0x180014008  jz      short loc_18001405E
0x18001400a  mov     rax, [rbx]
0x18001400d  mov     rcx, rbx
0x180014010  mov     rax, [rax+8]
0x180014014  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014019  nop
0x18001401a  mov     rcx, [rbx+48h]; hObject
0x18001401e  lea     rax, [rcx-1]
0x180014022  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180014026  jbe     short loc_180014066
0x180014028  lea     rcx, [rbx+48h]; this
0x18001402c  mov     rax, [rcx]
0x18001402f  dec     rax
0x180014032  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180014036  jbe     short loc_180014072
0x180014038  lea     rax, ??_7CCriticalSectionObject@@6B@; const CCriticalSectionObject::`vftable'
0x18001403f  mov     [rbx], rax
0x180014042  cmp     dword ptr [rbx+30h], 0
0x180014046  jnz     short loc_180014053
0x180014048  lea     rcx, [rbx+8]; lpCriticalSection
0x18001404c  call    cs:__imp_DeleteCriticalSection
0x180014052  nop
0x180014053  mov     rbx, [rsp+28h+arg_0]
0x180014058  add     rsp, 20h
0x18001405c  pop     rdi
0x18001405d  retn
0x18001405e  call    cs:__imp_GetLastError
0x180014064  jmp     short loc_18001400A
0x180014066  call    cs:__imp_CloseHandle
0x18001406c  mov     [rbx+48h], rdi
0x180014070  jmp     short loc_180014028
0x180014072  call    ?Close@CHandleObject@@QEAAKXZ; CHandleObject::Close(void)
0x180014077  jmp     short loc_180014038
```
