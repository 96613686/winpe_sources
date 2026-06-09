# TaskHelper::SetIsLogonTriggerEnabled(bool)

- ea: `0x140013f5c`
- end: `0x140013fda`
- name: `?SetIsLogonTriggerEnabled@TaskHelper@@QEAAJ_N@Z`
- size: `126`
- prototype: `int(TaskHelper *__hidden this, bool)`
- caller_count: `3`
- callee_count: `4`
- tags: `service_task, installer_update`

## callers

- `0x14000f2a4`
- `0x1400100e0`
- `0x140010ac0`

## callees

- `0x14000a4bc`
- `0x14001376c`
- `0x140013f5c`
- `0x14001a010`

## string_xrefs

- `0x140013f86`: `onecore\windows\directx\database\updater\exe\taskschedulerhelper.cpp`

## pseudocode

```c
__int64 __fastcall TaskHelper::SetIsLogonTriggerEnabled(LPVOID *this, unsigned __int8 a2)
{
  int v4; // ebx
  __int64 v5; // rdx
  int v7; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  v4 = TaskHelper::Init(this);
  if ( v4 < 0 )
  {
    v5 = 62;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v5,
      (unsigned int)"onecore\\windows\\directx\\database\\updater\\exe\\taskschedulerhelper.cpp",
      (const char *)(unsigned int)v4,
      v7);
    return (unsigned int)v4;
  }
  v4 = (*(__int64 (__fastcall **)(LPVOID, _QWORD))(*(_QWORD *)this[4] + 152LL))(
         this[4],
         (unsigned __int16)((a2 ^ 1) - 1));
  if ( v4 < 0 )
  {
    v5 = 64;
    goto LABEL_3;
  }
  *((_BYTE *)this + 40) = 1;
  return 0;
}

```

## disassembly

```asm
0x140013f5c  mov     [rsp+arg_0], rbx
0x140013f61  mov     [rsp+arg_8], rsi
0x140013f66  push    rdi; int
0x140013f67  sub     rsp, 20h
0x140013f6b  mov     sil, dl
0x140013f6e  mov     rdi, rcx
0x140013f71  call    ?Init@TaskHelper@@AEAAJXZ; TaskHelper::Init(void)
0x140013f76  mov     ebx, eax
0x140013f78  test    eax, eax
0x140013f7a  jns     short loc_140013F99
0x140013f7c  mov     edx, 3Eh ; '>'; void *
0x140013f81  mov     rcx, [rsp+28h]; this
0x140013f86  lea     r8, aOnecoreWindows_0; "onecore\\windows\\directx\\database\\up"...
0x140013f8d  mov     r9d, ebx; char *
0x140013f90  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140013f95  mov     eax, ebx
0x140013f97  jmp     short loc_140013FCA
0x140013f99  mov     rcx, [rdi+20h]
0x140013f9d  xor     sil, 1
0x140013fa1  movzx   edx, sil
0x140013fa5  dec     dx
0x140013fa8  mov     rax, [rcx]
0x140013fab  mov     rax, [rax+98h]
0x140013fb2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140013fb7  mov     ebx, eax
0x140013fb9  test    eax, eax
0x140013fbb  jns     short loc_140013FC4
0x140013fbd  mov     edx, 40h ; '@'
0x140013fc2  jmp     short loc_140013F81
0x140013fc4  mov     byte ptr [rdi+28h], 1
0x140013fc8  xor     eax, eax
0x140013fca  mov     rbx, [rsp+28h+arg_0]
0x140013fcf  mov     rsi, [rsp+28h+arg_8]
0x140013fd4  add     rsp, 20h
0x140013fd8  pop     rdi
0x140013fd9  retn
```
