# ATL::CAutoPtr<ATL::CDacl::CAccessAce>::~CAutoPtr<ATL::CDacl::CAccessAce>(void)

- ea: `0x140012f90`
- end: `0x140012fbf`
- name: `??1?$CAutoPtr@VCAccessAce@CDacl@ATL@@@ATL@@QEAA@XZ`
- size: `47`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x140015afa`

## callees

- `0x140012f90`
- `0x140014c70`

## pseudocode

```c
__int64 __fastcall ATL::CAutoPtr<ATL::CDacl::CAccessAce>::~CAutoPtr<ATL::CDacl::CAccessAce>(
        __int64 (__fastcall ****a1)(_QWORD, __int64))
{
  __int64 (__fastcall ***v2)(_QWORD, __int64); // rcx
  __int64 result; // rax

  v2 = *a1;
  if ( v2 )
    result = (**v2)(v2, 1);
  *a1 = 0;
  return result;
}

```

## disassembly

```asm
0x140012f90  push    rbx
0x140012f92  sub     rsp, 20h
0x140012f96  mov     rbx, rcx
0x140012f99  mov     rcx, [rcx]
0x140012f9c  test    rcx, rcx
0x140012f9f  jz      short loc_140012FB2
0x140012fa1  mov     rax, [rcx]
0x140012fa4  mov     edx, 1
0x140012fa9  mov     rax, [rax]
0x140012fac  call    cs:__guard_dispatch_icall_fptr
0x140012fb2  mov     qword ptr [rbx], 0
0x140012fb9  add     rsp, 20h
0x140012fbd  pop     rbx
0x140012fbe  retn
```
