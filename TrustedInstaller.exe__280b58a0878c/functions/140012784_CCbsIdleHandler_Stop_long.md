# CCbsIdleHandler::Stop(long *)

- ea: `0x140012784`
- end: `0x1400127c0`
- name: `?Stop@CCbsIdleHandler@@UEAAJPEAJ@Z`
- size: `60`
- prototype: `__int64 __fastcall(CCbsIdleHandler *__hidden this, int *)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, installer_update`

## callers

- `0x140012770`

## callees

- `0x1400127c8`
- `0x140017658`

## string_xrefs

- `0x140012791`: `Idle scavenging/repair stop signaled.`

## pseudocode

```c
__int64 __fastcall CCbsIdleHandler::Stop(CCbsIdleHandler *this, int *a2)
{
  __int64 result; // rax

  CBSWdsLogLight(0x4000000u, 0, 0, "Idle scavenging/repair stop signaled.");
  result = CCbsIdleHandler::StopScavenging((CCbsIdleHandler *)((char *)this - 56));
  *a2 = result;
  return result;
}

```

## disassembly

```asm
0x140012784  mov     [rsp+arg_0], rbx
0x140012789  push    rdi
0x14001278a  sub     rsp, 20h
0x14001278e  mov     rdi, rdx
0x140012791  lea     r9, aIdleScavenging; "Idle scavenging/repair stop signaled."
0x140012798  mov     rbx, rcx
0x14001279b  xor     edx, edx
0x14001279d  mov     ecx, 4000000h
0x1400127a2  xor     r8d, r8d
0x1400127a5  call    ?CBSWdsLogLight@@YAXW4tagLOG_SETUPLOG_SEVERITY@@J_NPEBDZZ; CBSWdsLogLight(tagLOG_SETUPLOG_SEVERITY,long,bool,char const *,...)
0x1400127aa  lea     rcx, [rbx-38h]; this
0x1400127ae  call    ?StopScavenging@CCbsIdleHandler@@QEAAJXZ; CCbsIdleHandler::StopScavenging(void)
0x1400127b3  mov     rbx, [rsp+28h+arg_0]
0x1400127b8  mov     [rdi], eax
0x1400127ba  add     rsp, 20h
0x1400127be  pop     rdi
0x1400127bf  retn
```
