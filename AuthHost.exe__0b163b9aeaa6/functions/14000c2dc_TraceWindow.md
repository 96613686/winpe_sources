# _TraceWindow

- ea: `0x14000c2dc`
- end: `0x14000c348`
- name: `_TraceWindow`
- size: `108`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `8`
- callee_count: `3`
- tags: ``

## callers

- `0x140009dd0`
- `0x140009e50`
- `0x14000a210`
- `0x14000a330`
- `0x14000a4b0`
- `0x14000a950`
- `0x14000aa60`
- `0x14000abe0`

## callees

- `0x14000429c`
- `0x14000be88`
- `0x14000c2dc`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x14000c341`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall TraceWindow(OLECHAR *a1)
{
  wchar_t *v1; // [rsp+30h] [rbp+8h] BYREF

  v1 = 0;
  if ( a1 )
  {
    if ( (int)GetWindowTitle(a1, &v1) >= 0
      && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 5u )
    {
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 7), 0xBu, &WPP_eb10dd10cfca36d0d06c224971275cc2_Traceguids, v1);
    }
    a1 = v1;
  }
  SysFreeString(a1);
}

```

## disassembly

```asm
0x14000c2dc  sub     rsp, 28h
0x14000c2e0  mov     [rsp+28h+arg_0], 0
0x14000c2e9  test    rcx, rcx
0x14000c2ec  jnz     short loc_14000C2F0
0x14000c2ee  jmp     short loc_14000C33D
0x14000c2f0  lea     rdx, [rsp+28h+arg_0]
0x14000c2f5  call    _GetWindowTitle
0x14000c2fa  test    eax, eax
0x14000c2fc  js      short loc_14000C338
0x14000c2fe  lea     rax, WPP_GLOBAL_Control
0x14000c305  mov     rcx, cs:WPP_GLOBAL_Control
0x14000c30c  cmp     rcx, rax
0x14000c30f  jz      short loc_14000C338
0x14000c311  test    byte ptr [rcx+44h], 4
0x14000c315  jz      short loc_14000C338
0x14000c317  cmp     byte ptr [rcx+41h], 5
0x14000c31b  jb      short loc_14000C338
0x14000c31d  mov     edx, 0Bh
0x14000c322  mov     r9, [rsp+28h+arg_0]
0x14000c327  lea     r8, WPP_eb10dd10cfca36d0d06c224971275cc2_Traceguids
0x14000c32e  mov     rcx, [rcx+38h]
0x14000c332  call    WPP_SF_S
0x14000c337  nop
0x14000c338  mov     rcx, [rsp+28h+arg_0]
0x14000c33d  add     rsp, 28h
0x14000c341  jmp     cs:__imp_SysFreeString
```
