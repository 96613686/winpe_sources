# CNTService::OnInit(void)

- ea: `0x1400056a0`
- end: `0x1400056ba`
- name: `?OnInit@CNTService@@UEAAHXZ`
- size: `26`
- prototype: `__int64 __fastcall(CNTService *__hidden this)`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task`

## callees

- `0x1400036a0`

## string_xrefs

- `0x1400056a4`: `CNTService::OnInit\n`

## pseudocode

```c
__int64 __fastcall CNTService::OnInit(CNTService *this)
{
  DEBUGMSG(L"CNTService::OnInit\n");
  return 1;
}

```

## disassembly

```asm
0x1400056a0  sub     rsp, 28h
0x1400056a4  lea     rcx, aCntserviceOnin; "CNTService::OnInit\n"
0x1400056ab  call    ?DEBUGMSG@@YAXPEBGZZ; DEBUGMSG(ushort const *,...)
0x1400056b0  mov     eax, 1
0x1400056b5  add     rsp, 28h
0x1400056b9  retn
```
