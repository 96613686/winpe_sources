# PoolNotify::PoolNotify(void)

- ea: `0x140001eb0`
- end: `0x140001f54`
- name: `??0PoolNotify@@QEAA@XZ`
- size: `164`
- prototype: `PoolNotify *__fastcall(PoolNotify *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x140002868`

## callees

- `0x140001eb0`
- `0x1400145a8`
- `0x140014690`

## import_xrefs

- `KERNEL32!CreateEventW` at `0x140001eff`
- `KERNEL32!CreateEventW` at `0x140001f13`
- `KERNEL32!CreateEventW` at `0x140001eff`
- `KERNEL32!CreateEventW` at `0x140001f13`
- `KERNEL32!InitializeCriticalSectionAndSpinCount` at `0x140001f26`
- `KERNEL32!InitializeCriticalSectionAndSpinCount` at `0x140001f26`

## pseudocode

```c
PoolNotify *__fastcall PoolNotify::PoolNotify(PoolNotify *this)
{
  BOOL v2; // edi

  *(_DWORD *)this = 0;
  *((_QWORD *)this + 1) = 0;
  *((_QWORD *)this + 2) = 0;
  *((_QWORD *)this + 3) = 0;
  v2 = 1;
  *((_DWORD *)this + 8) = 0;
  *((_DWORD *)this + 20) = 0;
  *(_QWORD *)((char *)this + 84) = 300;
  *((_QWORD *)this + 2) = CreateEventW(0, 1, 0, 0);
  *((_QWORD *)this + 3) = CreateEventW(0, 0, 0, 0);
  *((_DWORD *)this + 20) = InitializeCriticalSectionAndSpinCount((LPCRITICAL_SECTION)this + 1, 0x1000u);
  if ( (unsigned int)IsServer() )
    v2 = IsSBSSku() != 0;
  *((_DWORD *)this + 23) = v2;
  return this;
}

```

## disassembly

```asm
0x140001eb0  mov     [rsp+arg_0], rbx
0x140001eb5  push    rdi
0x140001eb6  sub     rsp, 20h
0x140001eba  xor     r9d, r9d; lpName
0x140001ebd  mov     dword ptr [rcx], 0
0x140001ec3  mov     rbx, rcx
0x140001ec6  mov     qword ptr [rcx+8], 0
0x140001ece  mov     qword ptr [rcx+10h], 0
0x140001ed6  xor     r8d, r8d; bInitialState
0x140001ed9  mov     qword ptr [rcx+18h], 0
0x140001ee1  lea     edi, [r9+1]
0x140001ee5  mov     dword ptr [rcx+20h], 0
0x140001eec  mov     dword ptr [rcx+50h], 0
0x140001ef3  mov     edx, edi; bManualReset
0x140001ef5  mov     qword ptr [rcx+54h], 12Ch
0x140001efd  xor     ecx, ecx; lpEventAttributes
0x140001eff  call    cs:__imp_CreateEventW
0x140001f05  xor     r9d, r9d; lpName
0x140001f08  xor     r8d, r8d; bInitialState
0x140001f0b  xor     edx, edx; bManualReset
0x140001f0d  mov     [rbx+10h], rax
0x140001f11  xor     ecx, ecx; lpEventAttributes
0x140001f13  call    cs:__imp_CreateEventW
0x140001f19  lea     rcx, [rbx+28h]; lpCriticalSection
0x140001f1d  mov     edx, 1000h; dwSpinCount
0x140001f22  mov     [rbx+18h], rax
0x140001f26  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x140001f2c  mov     [rbx+50h], eax
0x140001f2f  call    ?IsServer@@YAHXZ; IsServer(void)
0x140001f34  test    eax, eax
0x140001f36  jz      short loc_140001F43
0x140001f38  call    ?IsSBSSku@@YAHXZ; IsSBSSku(void)
0x140001f3d  test    eax, eax
0x140001f3f  jnz     short loc_140001F43
0x140001f41  xor     edi, edi
0x140001f43  mov     [rbx+5Ch], edi
0x140001f46  mov     rax, rbx
0x140001f49  mov     rbx, [rsp+28h+arg_0]
0x140001f4e  add     rsp, 20h
0x140001f52  pop     rdi
0x140001f53  retn
```
