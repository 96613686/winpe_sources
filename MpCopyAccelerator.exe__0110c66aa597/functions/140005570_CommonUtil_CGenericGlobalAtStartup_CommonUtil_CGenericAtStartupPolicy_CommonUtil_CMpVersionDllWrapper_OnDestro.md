# CommonUtil::CGenericGlobalAtStartup<CommonUtil::CGenericAtStartupPolicy<CommonUtil::CMpVersionDllWrapper>>::OnDestroy(tagMP_AT_STARTUP_TYPE *)

- ea: `0x140005570`
- end: `0x140005599`
- name: `?OnDestroy@?$CGenericGlobalAtStartup@U?$CGenericAtStartupPolicy@VCMpVersionDllWrapper@CommonUtil@@@CommonUtil@@@CommonUtil@@CAXPEAUtagMP_AT_STARTUP_TYPE@@@Z`
- size: `41`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x1400054e8`
- `0x140005570`

## pseudocode

```c
__int64 __fastcall CommonUtil::CGenericGlobalAtStartup<CommonUtil::CGenericAtStartupPolicy<CommonUtil::CMpVersionDllWrapper>>::OnDestroy(
        __int64 a1)
{
  __int64 v1; // rbx
  __int64 result; // rax

  v1 = a1 - 8;
  if ( *(_BYTE *)(a1 - 8 + 40) )
  {
    *(_BYTE *)(v1 + 40) = 0;
    CommonUtil::CMpVersionDllWrapper::`scalar deleting destructor'((HMODULE *)(a1 - 8), 0);
    result = 0;
    *(_QWORD *)v1 = 0;
  }
  return result;
}

```

## disassembly

```asm
0x140005570  push    rbx
0x140005572  sub     rsp, 20h
0x140005576  lea     rbx, [rcx-8]
0x14000557a  cmp     byte ptr [rbx+28h], 0
0x14000557e  jz      short loc_140005593
0x140005580  xor     edx, edx; unsigned int
0x140005582  mov     byte ptr [rbx+28h], 0
0x140005586  mov     rcx, rbx; this
0x140005589  call    ??_GCMpVersionDllWrapper@CommonUtil@@QEAAPEAXI@Z; CommonUtil::CMpVersionDllWrapper::`scalar deleting destructor'(uint)
0x14000558e  xor     eax, eax
0x140005590  mov     [rbx], rax
0x140005593  add     rsp, 20h
0x140005597  pop     rbx
0x140005598  retn
```
