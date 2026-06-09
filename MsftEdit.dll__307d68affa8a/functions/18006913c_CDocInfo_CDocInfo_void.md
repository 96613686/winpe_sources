# CDocInfo::~CDocInfo(void)

- ea: `0x18006913c`
- end: `0x180069277`
- name: `??1CDocInfo@@QEAA@XZ`
- size: `315`
- prototype: `void __fastcall(CDocInfo *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x18010bd8c`

## callees

- `0x180021928`
- `0x18006913c`
- `0x1800693d4`
- `0x1800693ec`
- `0x18013bea0`
- `0x18027a010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180069166`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180069170`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18006917a`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180069187`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180069166`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180069170`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18006917a`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180069187`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180069219`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180069219`
- `ext-ms-win-rtcore-gdi-object-l1-1-0!DeleteObject` at `0x180069248`
- `ext-ms-win-rtcore-gdi-object-l1-1-0!DeleteObject` at `0x180069248`

## pseudocode

```c
void __fastcall CDocInfo::~CDocInfo(CDocInfo *this)
{
  unsigned __int16 *v2; // rcx
  void *v3; // rcx
  __int64 v4; // rcx
  void *v5; // rcx
  __int64 v6; // rcx
  __int64 v7; // rcx
  void *v8; // rdi
  _QWORD *v9; // rcx

  v2 = *(unsigned __int16 **)this;
  if ( v2 )
    CW32System::SysFreeString(v2);
  v3 = (void *)*((_QWORD *)this + 3);
  if ( v3 )
    CloseHandle(v3);
  free(*((void **)this + 4));
  free(*((void **)this + 5));
  free(*((void **)this + 6));
  free(*((void **)this + 31));
  v4 = *((_QWORD *)this + 35);
  if ( v4 && !(*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4) )
    *((_QWORD *)this + 35) = 0;
  v5 = (void *)*((_QWORD *)this + 12);
  if ( v5 )
    DeleteObject(v5);
  v6 = *((_QWORD *)this + 13);
  if ( v6 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
  CW32System::GlobalFree(*((void **)this + 11));
  v7 = *((_QWORD *)this + 7);
  if ( v7 )
    (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v7 + 216LL))(v7, 1);
  v8 = (void *)*((_QWORD *)this + 1);
  if ( v8 )
  {
    CTxtStories::~CTxtStories(*((CTxtStories **)this + 1));
    operator delete(v8, 0x28u);
  }
  v9 = (_QWORD *)*((_QWORD *)this + 10);
  if ( v9 )
  {
    *v9 = 0;
    operator delete(v9, 0x18u);
  }
}

```

## disassembly

```asm
0x18006913c  mov     [rsp+arg_0], rbx
0x180069141  push    rdi
0x180069142  sub     rsp, 20h
0x180069146  mov     rbx, rcx
0x180069149  mov     rcx, [rcx]; unsigned __int16 *
0x18006914c  test    rcx, rcx
0x18006914f  jnz     loc_18006920F
0x180069155  mov     rcx, [rbx+18h]; hObject
0x180069159  test    rcx, rcx
0x18006915c  jnz     loc_180069219
0x180069162  mov     rcx, [rbx+20h]; Block
0x180069166  call    cs:__imp_free
0x18006916c  mov     rcx, [rbx+28h]; Block
0x180069170  call    cs:__imp_free
0x180069176  mov     rcx, [rbx+30h]; Block
0x18006917a  call    cs:__imp_free
0x180069180  mov     rcx, [rbx+0F8h]; Block
0x180069187  call    cs:__imp_free
0x18006918d  mov     rcx, [rbx+118h]
0x180069194  test    rcx, rcx
0x180069197  jnz     loc_180069224
0x18006919d  mov     rcx, [rbx+60h]; ho
0x1800691a1  test    rcx, rcx
0x1800691a4  jnz     loc_180069248
0x1800691aa  mov     rcx, [rbx+68h]
0x1800691ae  test    rcx, rcx
0x1800691b1  jnz     loc_180069253
0x1800691b7  mov     rcx, [rbx+58h]; void *
0x1800691bb  call    ?GlobalFree@CW32System@@SAPEAXPEAX@Z; CW32System::GlobalFree(void *)
0x1800691c0  mov     rcx, [rbx+38h]
0x1800691c4  test    rcx, rcx
0x1800691c7  jz      short loc_1800691DD
0x1800691c9  mov     rax, [rcx]
0x1800691cc  mov     edx, 1
0x1800691d1  mov     rax, [rax+0D8h]
0x1800691d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800691dd  mov     rdi, [rbx+8]
0x1800691e1  test    rdi, rdi
0x1800691e4  jz      short loc_1800691FB
0x1800691e6  mov     rcx, rdi; this
0x1800691e9  call    ??1CTxtStories@@QEAA@XZ; CTxtStories::~CTxtStories(void)
0x1800691ee  mov     edx, 28h ; '('; unsigned __int64
0x1800691f3  mov     rcx, rdi; void *
0x1800691f6  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800691fb  mov     rcx, [rbx+50h]; void *
0x1800691ff  test    rcx, rcx
0x180069202  jnz     short loc_180069264
0x180069204  mov     rbx, [rsp+28h+arg_0]
0x180069209  add     rsp, 20h
0x18006920d  pop     rdi
0x18006920e  retn
0x18006920f  call    ?SysFreeString@CW32System@@SAXPEAG@Z; CW32System::SysFreeString(ushort *)
0x180069214  jmp     loc_180069155
0x180069219  call    cs:__imp_CloseHandle
0x18006921f  jmp     loc_180069162
0x180069224  mov     rax, [rcx]
0x180069227  mov     rax, [rax+10h]
0x18006922b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180069230  test    eax, eax
0x180069232  jnz     loc_18006919D
0x180069238  mov     qword ptr [rbx+118h], 0
0x180069243  jmp     loc_18006919D
0x180069248  call    cs:__imp_DeleteObject
0x18006924e  jmp     loc_1800691AA
0x180069253  mov     rax, [rcx]
0x180069256  mov     rax, [rax+10h]
0x18006925a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006925f  jmp     loc_1800691B7
0x180069264  mov     edx, 18h; unsigned __int64
0x180069269  mov     qword ptr [rcx], 0
0x180069270  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180069275  jmp     short loc_180069204
```
