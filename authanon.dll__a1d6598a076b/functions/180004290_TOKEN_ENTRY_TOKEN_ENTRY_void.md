# TOKEN_ENTRY::~TOKEN_ENTRY(void)

- ea: `0x180004290`
- end: `0x18000430d`
- name: `??1TOKEN_ENTRY@@EEAA@XZ`
- size: `125`
- prototype: `void __fastcall(TOKEN_ENTRY *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180004380`

## callees

- `0x180004290`
- `0x180004314`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800042c3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800042df`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800042c3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800042df`
- `iisutil!??1CSmallSpinLock@@QEAA@XZ` at `0x1800042f4`
- `iisutil!??1CSmallSpinLock@@QEAA@XZ` at `0x1800042f4`

## pseudocode

```c
void __fastcall TOKEN_ENTRY::~TOKEN_ENTRY(TOKEN_ENTRY *this)
{
  void *v2; // rcx
  _BYTE *v3; // rdi
  void *v4; // rcx

  *((_DWORD *)this + 2) = 1852534644;
  *(_QWORD *)this = &TOKEN_ENTRY::`vftable';
  v2 = (void *)*((_QWORD *)this + 2);
  v3 = (char *)this + 260;
  if ( v2 )
  {
    if ( (*v3 & 1) != 0 )
      CloseHandle(v2);
    *((_QWORD *)this + 2) = 0;
  }
  v4 = (void *)*((_QWORD *)this + 3);
  if ( v4 )
  {
    if ( (*v3 & 2) != 0 )
      CloseHandle(v4);
    *((_QWORD *)this + 3) = 0;
  }
  CSmallSpinLock::~CSmallSpinLock((TOKEN_ENTRY *)((char *)this + 248));
  TOKEN_KEY::~TOKEN_KEY((TOKEN_ENTRY *)((char *)this + 120));
}

```

## disassembly

```asm
0x180004290  mov     [rsp+arg_0], rbx
0x180004295  push    rdi
0x180004296  sub     rsp, 20h
0x18000429a  mov     rbx, rcx
0x18000429d  mov     dword ptr [rcx+8], 6E6B6F74h
0x1800042a4  lea     rax, ??_7TOKEN_ENTRY@@6B@; const TOKEN_ENTRY::`vftable'
0x1800042ab  mov     [rcx], rax
0x1800042ae  mov     rcx, [rcx+10h]; hObject
0x1800042b2  lea     rdi, [rbx+104h]
0x1800042b9  test    rcx, rcx
0x1800042bc  jz      short loc_1800042D1
0x1800042be  test    byte ptr [rdi], 1
0x1800042c1  jz      short loc_1800042C9
0x1800042c3  call    cs:__imp_CloseHandle
0x1800042c9  mov     qword ptr [rbx+10h], 0
0x1800042d1  mov     rcx, [rbx+18h]; hObject
0x1800042d5  test    rcx, rcx
0x1800042d8  jz      short loc_1800042ED
0x1800042da  test    byte ptr [rdi], 2
0x1800042dd  jz      short loc_1800042E5
0x1800042df  call    cs:__imp_CloseHandle
0x1800042e5  mov     qword ptr [rbx+18h], 0
0x1800042ed  lea     rcx, [rbx+0F8h]
0x1800042f4  call    cs:__imp_??1CSmallSpinLock@@QEAA@XZ; CSmallSpinLock::~CSmallSpinLock(void)
0x1800042fa  lea     rcx, [rbx+78h]; this
0x1800042fe  mov     rbx, [rsp+28h+arg_0]
0x180004303  add     rsp, 20h
0x180004307  pop     rdi
0x180004308  jmp     ??1TOKEN_KEY@@QEAA@XZ; TOKEN_KEY::~TOKEN_KEY(void)
```
