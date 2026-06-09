# CDriveConfiguration::Cleanup(void)

- ea: `0x18000f360`
- end: `0x18000f3ec`
- name: `?Cleanup@CDriveConfiguration@@AEAAXXZ`
- size: `140`
- prototype: `void __fastcall(CDriveConfiguration *__hidden this)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18000f150`
- `0x1800101a0`

## callees

- `0x18000f360`
- `0x18001358e`
- `0x180015010`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x18000f377`
- `KERNEL32!EnterCriticalSection` at `0x18000f377`
- `KERNEL32!LeaveCriticalSection` at `0x18000f3c7`
- `KERNEL32!LeaveCriticalSection` at `0x18000f3c7`

## pseudocode

```c
void __fastcall CDriveConfiguration::Cleanup(CDriveConfiguration *this)
{
  __int64 v2; // rcx
  __int64 v3; // rcx

  if ( *(_BYTE *)this )
  {
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
    v2 = *((_QWORD *)this + 159);
    if ( v2 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 16LL))(v2);
      *((_QWORD *)this + 159) = 0;
    }
    v3 = *((_QWORD *)this + 160);
    if ( v3 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 40LL))(v3);
      *((_QWORD *)this + 160) = 0;
    }
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
    memset_0((char *)this + 64, 0, 0x458u);
    *(_BYTE *)this = 0;
  }
}

```

## disassembly

```asm
0x18000f360  mov     [rsp+arg_0], rbx
0x18000f365  push    rdi
0x18000f366  sub     rsp, 20h
0x18000f36a  mov     al, [rcx]
0x18000f36c  mov     rbx, rcx
0x18000f36f  test    al, al
0x18000f371  jz      short loc_18000F3E1
0x18000f373  add     rcx, 18h; lpCriticalSection
0x18000f377  call    cs:__imp_EnterCriticalSection
0x18000f37d  mov     rcx, [rbx+4F8h]
0x18000f384  test    rcx, rcx
0x18000f387  jz      short loc_18000F3A0
0x18000f389  mov     rax, [rcx]
0x18000f38c  mov     rax, [rax+10h]
0x18000f390  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f395  mov     qword ptr [rbx+4F8h], 0
0x18000f3a0  mov     rcx, [rbx+500h]
0x18000f3a7  test    rcx, rcx
0x18000f3aa  jz      short loc_18000F3C3
0x18000f3ac  mov     rax, [rcx]
0x18000f3af  mov     rax, [rax+28h]
0x18000f3b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f3b8  mov     qword ptr [rbx+500h], 0
0x18000f3c3  lea     rcx, [rbx+18h]; lpCriticalSection
0x18000f3c7  call    cs:__imp_LeaveCriticalSection
0x18000f3cd  lea     rcx, [rbx+40h]; void *
0x18000f3d1  xor     edx, edx; Val
0x18000f3d3  mov     r8d, 458h; Size
0x18000f3d9  call    memset_0
0x18000f3de  mov     byte ptr [rbx], 0
0x18000f3e1  mov     rbx, [rsp+28h+arg_0]
0x18000f3e6  add     rsp, 20h
0x18000f3ea  pop     rdi
0x18000f3eb  retn
```
