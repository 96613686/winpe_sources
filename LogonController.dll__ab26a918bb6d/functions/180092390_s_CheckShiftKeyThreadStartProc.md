# s_CheckShiftKeyThreadStartProc

- ea: `0x180092390`
- end: `0x1800923e8`
- name: `s_CheckShiftKeyThreadStartProc`
- size: `88`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180092390`

## import_xrefs

- `ext-ms-win-ntuser-keyboard-l1-1-0!GetAsyncKeyState` at `0x1800923c6`
- `ext-ms-win-ntuser-keyboard-l1-1-0!GetAsyncKeyState` at `0x1800923c6`
- `USER32!OpenInputDesktop` at `0x1800923aa`
- `USER32!OpenInputDesktop` at `0x1800923aa`
- `USER32!SetThreadDesktop` at `0x1800923bb`
- `USER32!SetThreadDesktop` at `0x1800923bb`
- `USER32!CloseDesktop` at `0x1800923d5`
- `USER32!CloseDesktop` at `0x1800923d5`

## pseudocode

```c
__int64 __fastcall s_CheckShiftKeyThreadStartProc(bool *Parameter)
{
  HDESK v2; // rax
  HDESK v3; // rbx

  *Parameter = 0;
  v2 = OpenInputDesktop(0, 0, 0x10000000u);
  v3 = v2;
  if ( v2 )
  {
    SetThreadDesktop(v2);
    *Parameter = GetAsyncKeyState(16) < 0;
    CloseDesktop(v3);
  }
  return 0;
}

```

## disassembly

```asm
0x180092390  mov     [rsp+arg_0], rbx
0x180092395  push    rdi
0x180092396  sub     rsp, 20h
0x18009239a  mov     rdi, rcx
0x18009239d  mov     byte ptr [rcx], 0
0x1800923a0  xor     ecx, ecx; dwFlags
0x1800923a2  xor     edx, edx; fInherit
0x1800923a4  mov     r8d, 10000000h; dwDesiredAccess
0x1800923aa  call    cs:__imp_OpenInputDesktop
0x1800923b0  mov     rbx, rax
0x1800923b3  test    rax, rax
0x1800923b6  jz      short loc_1800923DB
0x1800923b8  mov     rcx, rax; hDesktop
0x1800923bb  call    cs:__imp_SetThreadDesktop
0x1800923c1  mov     ecx, 10h; vKey
0x1800923c6  call    cs:__imp_GetAsyncKeyState
0x1800923cc  shr     ax, 0Fh
0x1800923d0  mov     rcx, rbx; hDesktop
0x1800923d3  mov     [rdi], al
0x1800923d5  call    cs:__imp_CloseDesktop
0x1800923db  mov     rbx, [rsp+28h+arg_0]
0x1800923e0  xor     eax, eax
0x1800923e2  add     rsp, 20h
0x1800923e6  pop     rdi
0x1800923e7  retn
```
