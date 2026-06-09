# Windows::Storage::StateABIImplementation::SetVersionOperation::AcquireLock(void)

- ea: `0x18003bc00`
- end: `0x18003bc7d`
- name: `?AcquireLock@SetVersionOperation@StateABIImplementation@Storage@Windows@@IEAAJXZ`
- size: `125`
- prototype: `HRESULT __fastcall(Windows::Storage::StateABIImplementation::SetVersionOperation *this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18001f770`

## callees

- `0x1800022b0`
- `0x18003bc00`

## import_xrefs

- `ext-ms-win-appmodel-state-ext-l1-2-0!CreateStateLock` at `0x18003bc1a`
- `ext-ms-win-appmodel-state-ext-l1-2-0!CreateStateLock` at `0x18003bc1a`
- `ext-ms-win-appmodel-state-ext-l1-2-0!AcquireStateLock` at `0x18003bc5d`
- `ext-ms-win-appmodel-state-ext-l1-2-0!AcquireStateLock` at `0x18003bc5d`

## string_xrefs

- `0x18003bc2c`: `CreateStateLock`

## pseudocode

```c
HRESULT __fastcall Windows::Storage::StateABIImplementation::SetVersionOperation::AcquireLock(
        Windows::Storage::StateABIImplementation::SetVersionOperation *this)
{
  _HSTATE_LOCK *StateLock; // rax
  void *retaddr; // [rsp+28h] [rbp+0h]

  if ( !this->m_hStateLock )
  {
    StateLock = (_HSTATE_LOCK *)CreateStateLock(this->m_applicationStateHandle);
    this->m_hStateLock = StateLock;
    if ( !StateLock )
      return wil::details::in1diag3::Return_GetLastErrorMsg(
               retaddr,
               0xE9u,
               "onecoreuap\\base\\appmodel\\statemanager\\winrt\\lib\\windows.storage.setversionoperation.cpp",
               "CreateStateLock");
  }
  if ( (unsigned int)AcquireStateLock(this->m_hStateLock, 0, 5000) )
    return 0;
  return wil::details::in1diag3::Return_GetLastErrorMsg(
           retaddr,
           0xEEu,
           "onecoreuap\\base\\appmodel\\statemanager\\winrt\\lib\\windows.storage.setversionoperation.cpp",
           "AcquireStateLock");
}

```

## disassembly

```asm
0x18003bc00  push    rbx
0x18003bc02  sub     rsp, 20h
0x18003bc06  cmp     qword ptr [this+0B0h], 0
0x18003bc0e  mov     rbx, this
0x18003bc11  jnz     short loc_18003BC4E
0x18003bc13  mov     this, [this+0A8h]
0x18003bc1a  call    cs:__imp_CreateStateLock
0x18003bc20  mov     [rbx+0B0h], rax
0x18003bc27  test    rax, rax
0x18003bc2a  jnz     short loc_18003BC4E
0x18003bc2c  lea     r9, aCreatestateloc_0; "CreateStateLock"
0x18003bc33  mov     edx, 0E9h
0x18003bc38  mov     this, [rsp+28h]
0x18003bc3d  lea     r8, aOnecoreuapBase_20; "onecoreuap\\base\\appmodel\\statemanage"...
0x18003bc44  add     rsp, 20h
0x18003bc48  pop     rbx
0x18003bc49  jmp     ?Return_GetLastErrorMsg@in1diag3@details@wil@@YAJPEAXIPEBD1ZZ; wil::details::in1diag3::Return_GetLastErrorMsg(void *,uint,char const *,char const *,...)
0x18003bc4e  mov     this, [rbx+0B0h]
0x18003bc55  xor     edx, edx
0x18003bc57  mov     r8d, 1388h
0x18003bc5d  call    cs:__imp_AcquireStateLock
0x18003bc63  test    eax, eax
0x18003bc65  jnz     short loc_18003BC75
0x18003bc67  lea     r9, aAcquirestatelo_0; "AcquireStateLock"
0x18003bc6e  mov     edx, 0EEh
0x18003bc73  jmp     short loc_18003BC38
0x18003bc75  xor     eax, eax
0x18003bc77  add     rsp, 20h
0x18003bc7b  pop     rbx
0x18003bc7c  retn
```
