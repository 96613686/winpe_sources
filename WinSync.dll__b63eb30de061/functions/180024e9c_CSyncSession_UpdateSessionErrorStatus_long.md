# CSyncSession::UpdateSessionErrorStatus(long)

- ea: `0x180024e9c`
- end: `0x180024f01`
- name: `?UpdateSessionErrorStatus@CSyncSession@@AEAAXJ@Z`
- size: `101`
- prototype: `void __fastcall(CSyncSession *__hidden this, int)`
- caller_count: `2`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x180020dac`
- `0x1800316f0`

## callees

- `0x18001a038`
- `0x180024e9c`

## string_xrefs

- `0x180024ece`: `CSyncSession::UpdateSessionErrorStatus`

## pseudocode

```c
void __fastcall CSyncSession::UpdateSessionErrorStatus(CSyncSession *this, int a2)
{
  __int64 v4; // rax

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_s(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      57,
      WPP_24b986413345305da18a80c41c45e189_Traceguids,
      "CSyncSession::UpdateSessionErrorStatus");
  }
  v4 = *((_QWORD *)this + 21);
  if ( *(int *)(v4 + 32) >= 0 )
    *(_DWORD *)(v4 + 32) = a2;
}

```

## disassembly

```asm
0x180024e9c  mov     [rsp+arg_0], rbx
0x180024ea1  push    rdi
0x180024ea2  sub     rsp, 20h
0x180024ea6  mov     ebx, edx
0x180024ea8  mov     rdi, rcx
0x180024eab  mov     rcx, cs:WPP_GLOBAL_Control
0x180024eb2  lea     rax, WPP_GLOBAL_Control
0x180024eb9  cmp     rcx, rax
0x180024ebc  jz      short loc_180024EE6
0x180024ebe  test    byte ptr [rcx+1Ch], 4
0x180024ec2  jz      short loc_180024EE6
0x180024ec4  cmp     byte ptr [rcx+19h], 5
0x180024ec8  jb      short loc_180024EE6
0x180024eca  mov     rcx, [rcx+10h]
0x180024ece  lea     r9, aCsyncsessionUp; "CSyncSession::UpdateSessionErrorStatus"
0x180024ed5  mov     edx, 39h ; '9'
0x180024eda  lea     r8, WPP_24b986413345305da18a80c41c45e189_Traceguids
0x180024ee1  call    WPP_SF_s
0x180024ee6  mov     rax, [rdi+0A8h]
0x180024eed  cmp     dword ptr [rax+20h], 0
0x180024ef1  jl      short loc_180024EF6
0x180024ef3  mov     [rax+20h], ebx
0x180024ef6  mov     rbx, [rsp+28h+arg_0]
0x180024efb  add     rsp, 20h
0x180024eff  pop     rdi
0x180024f00  retn
```
