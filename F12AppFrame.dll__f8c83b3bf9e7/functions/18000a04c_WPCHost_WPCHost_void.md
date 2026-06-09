# WPCHost::~WPCHost(void)

- ea: `0x18000a04c`
- end: `0x18000a0c8`
- name: `??1WPCHost@@QEAA@XZ`
- size: `124`
- prototype: `void __fastcall(WPCHost *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180009d14`

## callees

- `0x18000a04c`
- `0x180035010`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x18000a0bb`
- `KERNEL32!DeleteCriticalSection` at `0x18000a0bb`

## pseudocode

```c
void __fastcall WPCHost::~WPCHost(WPCHost *this)
{
  __int64 v2; // rcx
  __int64 v3; // rcx
  __int64 v4; // rcx
  __int64 v5; // rcx

  v2 = *((_QWORD *)this + 15);
  if ( v2 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 16LL))(v2);
  v3 = *((_QWORD *)this + 14);
  if ( v3 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 16LL))(v3);
  v4 = *((_QWORD *)this + 13);
  if ( v4 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
  v5 = *((_QWORD *)this + 12);
  if ( v5 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
  if ( *((_BYTE *)this + 88) )
  {
    *((_BYTE *)this + 88) = 0;
    DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 48));
  }
}

```

## disassembly

```asm
0x18000a04c  push    rbx
0x18000a04e  sub     rsp, 20h
0x18000a052  mov     rbx, rcx
0x18000a055  mov     rcx, [rcx+78h]
0x18000a059  test    rcx, rcx
0x18000a05c  jz      short loc_18000A06B
0x18000a05e  mov     rax, [rcx]
0x18000a061  mov     rax, [rax+10h]
0x18000a065  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a06a  nop
0x18000a06b  mov     rcx, [rbx+70h]
0x18000a06f  test    rcx, rcx
0x18000a072  jz      short loc_18000A081
0x18000a074  mov     rax, [rcx]
0x18000a077  mov     rax, [rax+10h]
0x18000a07b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a080  nop
0x18000a081  mov     rcx, [rbx+68h]
0x18000a085  test    rcx, rcx
0x18000a088  jz      short loc_18000A097
0x18000a08a  mov     rax, [rcx]
0x18000a08d  mov     rax, [rax+10h]
0x18000a091  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a096  nop
0x18000a097  mov     rcx, [rbx+60h]
0x18000a09b  test    rcx, rcx
0x18000a09e  jz      short loc_18000A0AD
0x18000a0a0  mov     rax, [rcx]
0x18000a0a3  mov     rax, [rax+10h]
0x18000a0a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a0ac  nop
0x18000a0ad  lea     rcx, [rbx+30h]; lpCriticalSection
0x18000a0b1  cmp     byte ptr [rcx+28h], 0
0x18000a0b5  jz      short loc_18000A0C2
0x18000a0b7  mov     byte ptr [rcx+28h], 0
0x18000a0bb  call    cs:__imp_DeleteCriticalSection
0x18000a0c1  nop
0x18000a0c2  add     rsp, 20h
0x18000a0c6  pop     rbx
0x18000a0c7  retn
```
