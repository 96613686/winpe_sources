# Windows::Detail::OnBlockExitImpl__lambda_8be974e518f233936c89a2634cdcf1eb___::_OnBlockExitImpl__lambda_8be974e518f233936c89a2634cdcf1eb___

- ea: `0x140009f04`
- end: `0x140009f40`
- name: `Windows::Detail::OnBlockExitImpl__lambda_8be974e518f233936c89a2634cdcf1eb___::_OnBlockExitImpl__lambda_8be974e518f233936c89a2634cdcf1eb___`
- size: `60`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x14000c8d0`

## callees

- `0x140009f04`
- `0x14000e328`

## string_xrefs

- `0x140009f23`: `Error: Not reversed from impersonation on func: %s`

## pseudocode

```c
void __fastcall Windows::Detail::OnBlockExitImpl__lambda_8be974e518f233936c89a2634cdcf1eb___::_OnBlockExitImpl__lambda_8be974e518f233936c89a2634cdcf1eb___(
        _BYTE *a1)
{
  if ( *a1 )
  {
    if ( NtCurrentTeb()->IsImpersonating )
      CBSWdsLog(
        0x4000000u,
        0,
        0,
        "Error: Not reversed from impersonation on func: %s",
        "CCbsWorker::StartupProcessingEx::<lambda_8be974e518f233936c89a2634cdcf1eb>::operator ()");
  }
}

```

## disassembly

```asm
0x140009f04  sub     rsp, 38h
0x140009f08  cmp     byte ptr [rcx], 0
0x140009f0b  jz      short loc_140009F3B
0x140009f0d  mov     eax, gs:179Ch
0x140009f15  test    eax, eax
0x140009f17  jz      short loc_140009F3B
0x140009f19  lea     rax, aCcbsworkerStar; "CCbsWorker::StartupProcessingEx::<lambd"...
0x140009f20  xor     r8d, r8d
0x140009f23  lea     r9, aErrorNotRevers; "Error: Not reversed from impersonation "...
0x140009f2a  mov     [rsp+38h+var_18], rax
0x140009f2f  xor     edx, edx
0x140009f31  mov     ecx, 4000000h
0x140009f36  call    ?CBSWdsLog@@YAXW4tagLOG_SETUPLOG_SEVERITY@@J_NPEBDZZ; CBSWdsLog(tagLOG_SETUPLOG_SEVERITY,long,bool,char const *,...)
0x140009f3b  add     rsp, 38h
0x140009f3f  retn
```
