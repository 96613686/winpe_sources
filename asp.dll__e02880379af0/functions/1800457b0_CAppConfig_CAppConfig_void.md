# CAppConfig::~CAppConfig(void)

- ea: `0x1800457b0`
- end: `0x180045818`
- name: `??1CAppConfig@@QEAA@XZ`
- size: `104`
- prototype: `void __fastcall(CAppConfig *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x18000f690`

## callees

- `0x1800457b0`

## import_xrefs

- `KERNEL32!GlobalFree` at `0x1800457cc`
- `KERNEL32!GlobalFree` at `0x1800457cc`
- `KERNEL32!CloseHandle` at `0x1800457f4`
- `KERNEL32!CloseHandle` at `0x1800457f4`
- `KERNEL32!DeleteCriticalSection` at `0x180045807`
- `KERNEL32!DeleteCriticalSection` at `0x180045807`

## pseudocode

```c
void __fastcall CAppConfig::~CAppConfig(CAppConfig *this)
{
  __int64 i; // rdi
  void *v3; // rcx
  void *v4; // rcx

  for ( i = 0; i != 4; ++i )
  {
    v3 = (void *)*((_QWORD *)this + i + 24);
    if ( v3 )
    {
      GlobalFree(v3);
      *((_QWORD *)this + i + 24) = 0;
    }
  }
  v4 = (void *)*((_QWORD *)this + 17);
  if ( v4 != (void *)-1LL )
    CloseHandle(v4);
  if ( (*((_BYTE *)this + 12) & 0x10) != 0 )
    DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 152));
}

```

## disassembly

```asm
0x1800457b0  mov     [rsp+arg_0], rbx
0x1800457b5  push    rdi
0x1800457b6  sub     rsp, 20h
0x1800457ba  mov     rbx, rcx
0x1800457bd  xor     edi, edi
0x1800457bf  mov     rcx, [rbx+rdi*8+0C0h]; hMem
0x1800457c7  test    rcx, rcx
0x1800457ca  jz      short loc_1800457DE
0x1800457cc  call    cs:__imp_GlobalFree
0x1800457d2  mov     qword ptr [rbx+rdi*8+0C0h], 0
0x1800457de  inc     rdi
0x1800457e1  cmp     rdi, 4
0x1800457e5  jnz     short loc_1800457BF
0x1800457e7  mov     rcx, [rbx+88h]; hObject
0x1800457ee  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x1800457f2  jz      short loc_1800457FA
0x1800457f4  call    cs:__imp_CloseHandle
0x1800457fa  test    byte ptr [rbx+0Ch], 10h
0x1800457fe  jz      short loc_18004580D
0x180045800  lea     rcx, [rbx+98h]; lpCriticalSection
0x180045807  call    cs:__imp_DeleteCriticalSection
0x18004580d  mov     rbx, [rsp+28h+arg_0]
0x180045812  add     rsp, 20h
0x180045816  pop     rdi
0x180045817  retn
```
