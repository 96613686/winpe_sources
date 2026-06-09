# CSyncChangeWrapper::SetTemporaryConstraintConflict(int)

- ea: `0x18006e568`
- end: `0x18006e601`
- name: `?SetTemporaryConstraintConflict@CSyncChangeWrapper@@QEAAXH@Z`
- size: `153`
- prototype: `void __fastcall(CSyncChangeWrapper *__hidden this, int)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18003ea50`

## callees

- `0x18001a038`
- `0x18006e568`

## string_xrefs

- `0x18006e59f`: `CSyncChangeWrapper::SetTemporaryConstraintConflict`
- `0x18006e5d9`: `CSyncChangeWrapper::SetTemporaryConstraintConflict`

## pseudocode

```c
void __fastcall CSyncChangeWrapper::SetTemporaryConstraintConflict(CSyncChangeWrapper *this, int a2)
{
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_s(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      96,
      WPP_1ce7e5fbf03e39cbecdc9dc9cb74efd7_Traceguids,
      "CSyncChangeWrapper::SetTemporaryConstraintConflict");
  }
  *((_DWORD *)this + 74) = a2;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_s(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      97,
      WPP_1ce7e5fbf03e39cbecdc9dc9cb74efd7_Traceguids,
      "CSyncChangeWrapper::SetTemporaryConstraintConflict");
  }
}

```

## disassembly

```asm
0x18006e568  mov     [rsp+arg_0], rbx
0x18006e56d  mov     [rsp+arg_8], rsi
0x18006e572  push    rdi
0x18006e573  sub     rsp, 20h
0x18006e577  mov     ebx, edx
0x18006e579  mov     rdi, rcx
0x18006e57c  mov     rcx, cs:WPP_GLOBAL_Control
0x18006e583  lea     rsi, WPP_GLOBAL_Control
0x18006e58a  cmp     rcx, rsi
0x18006e58d  jz      short loc_18006E5B7
0x18006e58f  test    byte ptr [rcx+1Ch], 8
0x18006e593  jz      short loc_18006E5B7
0x18006e595  cmp     byte ptr [rcx+19h], 5
0x18006e599  jb      short loc_18006E5B7
0x18006e59b  mov     rcx, [rcx+10h]
0x18006e59f  lea     r9, aCsyncchangewra_52; "CSyncChangeWrapper::SetTemporaryConstra"...
0x18006e5a6  mov     edx, 60h ; '`'
0x18006e5ab  lea     r8, WPP_1ce7e5fbf03e39cbecdc9dc9cb74efd7_Traceguids
0x18006e5b2  call    WPP_SF_s
0x18006e5b7  mov     [rdi+128h], ebx
0x18006e5bd  mov     rcx, cs:WPP_GLOBAL_Control
0x18006e5c4  cmp     rcx, rsi
0x18006e5c7  jz      short loc_18006E5F1
0x18006e5c9  test    byte ptr [rcx+1Ch], 8
0x18006e5cd  jz      short loc_18006E5F1
0x18006e5cf  cmp     byte ptr [rcx+19h], 5
0x18006e5d3  jb      short loc_18006E5F1
0x18006e5d5  mov     rcx, [rcx+10h]
0x18006e5d9  lea     r9, aCsyncchangewra_52; "CSyncChangeWrapper::SetTemporaryConstra"...
0x18006e5e0  mov     edx, 61h ; 'a'
0x18006e5e5  lea     r8, WPP_1ce7e5fbf03e39cbecdc9dc9cb74efd7_Traceguids
0x18006e5ec  call    WPP_SF_s
0x18006e5f1  mov     rbx, [rsp+28h+arg_0]
0x18006e5f6  mov     rsi, [rsp+28h+arg_8]
0x18006e5fb  add     rsp, 20h
0x18006e5ff  pop     rdi
0x18006e600  retn
```
