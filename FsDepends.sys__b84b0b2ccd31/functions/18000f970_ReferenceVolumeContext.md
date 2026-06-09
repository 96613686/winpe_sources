# ReferenceVolumeContext

- ea: `0x18000f970`
- end: `0x18000f9fe`
- name: `ReferenceVolumeContext`
- size: `142`
- prototype: `__int64 __fastcall(PFLT_CONTEXT Context)`
- caller_count: `11`
- callee_count: `1`
- tags: ``

## callers

- `0x18000844c`
- `0x180009840`
- `0x18000aa48`
- `0x18000bcc8`
- `0x18000c940`
- `0x18000cb40`
- `0x18000eac0`
- `0x18000f2e8`
- `0x180010e40`
- `0x180010fd0`
- `0x1800110c0`

## callees

- `0x18000f970`

## import_xrefs

- `FLTMGR!FltReferenceContext` at `0x18000f989`
- `FLTMGR!FltReferenceContext` at `0x18000f989`
- `FLTMGR!FltObjectReference` at `0x18000f999`
- `FLTMGR!FltObjectReference` at `0x18000f9af`
- `FLTMGR!FltObjectReference` at `0x18000f999`
- `FLTMGR!FltObjectReference` at `0x18000f9af`
- `FLTMGR!FltObjectDereference` at `0x18000f9c5`
- `FLTMGR!FltObjectDereference` at `0x18000f9c5`
- `FLTMGR!FltReleaseContext` at `0x18000f9d9`
- `FLTMGR!FltReleaseContext` at `0x18000f9d9`

## pseudocode

```c
__int64 __fastcall ReferenceVolumeContext(PFLT_CONTEXT Context, char a2)
{
  NTSTATUS v4; // edi

  if ( !a2 )
    FltReferenceContext(Context);
  v4 = FltObjectReference(*((PVOID *)Context + 9));
  if ( v4 >= 0 )
  {
    v4 = FltObjectReference(*((PVOID *)Context + 8));
    if ( v4 >= 0 )
    {
      _InterlockedIncrement((volatile signed __int32 *)Context + 29);
      return (unsigned int)v4;
    }
    FltObjectDereference(*((PVOID *)Context + 9));
  }
  if ( !a2 )
    FltReleaseContext(Context);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18000f970  mov     [rsp+arg_0], rbx
0x18000f975  mov     [rsp+arg_8], rsi
0x18000f97a  push    rdi
0x18000f97b  sub     rsp, 20h
0x18000f97f  mov     sil, dl
0x18000f982  mov     rbx, rcx
0x18000f985  test    dl, dl
0x18000f987  jnz     short loc_18000F995
0x18000f989  call    cs:__imp_FltReferenceContext
0x18000f990  nop     dword ptr [rax+rax+00h]
0x18000f995  mov     rcx, [rbx+48h]; FltObject
0x18000f999  call    cs:__imp_FltObjectReference
0x18000f9a0  nop     dword ptr [rax+rax+00h]
0x18000f9a5  mov     edi, eax
0x18000f9a7  test    eax, eax
0x18000f9a9  js      short loc_18000F9D1
0x18000f9ab  mov     rcx, [rbx+40h]; FltObject
0x18000f9af  call    cs:__imp_FltObjectReference
0x18000f9b6  nop     dword ptr [rax+rax+00h]
0x18000f9bb  mov     edi, eax
0x18000f9bd  test    eax, eax
0x18000f9bf  jns     short loc_18000F9F8
0x18000f9c1  mov     rcx, [rbx+48h]; FltObject
0x18000f9c5  call    cs:__imp_FltObjectDereference
0x18000f9cc  nop     dword ptr [rax+rax+00h]
0x18000f9d1  test    sil, sil
0x18000f9d4  jnz     short loc_18000F9E5
0x18000f9d6  mov     rcx, rbx; Context
0x18000f9d9  call    cs:__imp_FltReleaseContext
0x18000f9e0  nop     dword ptr [rax+rax+00h]
0x18000f9e5  mov     rbx, [rsp+28h+arg_0]
0x18000f9ea  mov     eax, edi
0x18000f9ec  mov     rsi, [rsp+28h+arg_8]
0x18000f9f1  add     rsp, 20h
0x18000f9f5  pop     rdi
0x18000f9f6  retn
0x18000f9f8  lock inc dword ptr [rbx+74h]
0x18000f9fc  jmp     short loc_18000F9E5
```
