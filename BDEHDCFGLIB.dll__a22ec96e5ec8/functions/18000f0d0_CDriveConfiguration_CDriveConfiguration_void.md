# CDriveConfiguration::CDriveConfiguration(void)

- ea: `0x18000f0d0`
- end: `0x18000f13b`
- name: `??0CDriveConfiguration@@QEAA@XZ`
- size: `107`
- prototype: `CDriveConfiguration *__fastcall(CDriveConfiguration *__hidden this)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x18001358e`

## import_xrefs

- `KERNEL32!InitializeCriticalSection` at `0x18000f12c`
- `KERNEL32!InitializeCriticalSection` at `0x18000f12c`

## pseudocode

```c
CDriveConfiguration *__fastcall CDriveConfiguration::CDriveConfiguration(CDriveConfiguration *this)
{
  *(_BYTE *)this = 0;
  *((_DWORD *)this + 1) = -1063256037;
  *((_DWORD *)this + 2) = -1063256037;
  *((_BYTE *)this + 12) = 0;
  *((_QWORD *)this + 157) = 0;
  *((_DWORD *)this + 316) = 0;
  *((_QWORD *)this + 159) = 0;
  *((_QWORD *)this + 160) = 0;
  *(_OWORD *)((char *)this + 1176) = 0;
  *(_OWORD *)((char *)this + 1192) = 0;
  memset_0((char *)this + 64, 0, 0x458u);
  InitializeCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
  return this;
}

```

## disassembly

```asm
0x18000f0d0  push    rbx
0x18000f0d2  sub     rsp, 20h
0x18000f0d6  mov     rbx, rcx
0x18000f0d9  mov     eax, 0C0A0001Bh
0x18000f0de  xor     ecx, ecx
0x18000f0e0  xorps   xmm0, xmm0
0x18000f0e3  xor     edx, edx; Val
0x18000f0e5  mov     r8d, 458h; Size
0x18000f0eb  mov     [rbx], cl
0x18000f0ed  mov     [rbx+4], eax
0x18000f0f0  mov     [rbx+8], eax
0x18000f0f3  mov     [rbx+0Ch], cl
0x18000f0f6  mov     [rbx+4E8h], rcx
0x18000f0fd  mov     [rbx+4F0h], ecx
0x18000f103  mov     [rbx+4F8h], rcx
0x18000f10a  mov     [rbx+500h], rcx
0x18000f111  lea     rcx, [rbx+40h]; void *
0x18000f115  movups  xmmword ptr [rbx+498h], xmm0
0x18000f11c  movups  xmmword ptr [rbx+4A8h], xmm0
0x18000f123  call    memset_0
0x18000f128  lea     rcx, [rbx+18h]; lpCriticalSection
0x18000f12c  call    cs:__imp_InitializeCriticalSection
0x18000f132  mov     rax, rbx
0x18000f135  add     rsp, 20h
0x18000f139  pop     rbx
0x18000f13a  retn
```
