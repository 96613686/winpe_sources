# McpService::GetMcpServiceType(_McpServiceType *)

- ea: `0x180025fc0`
- end: `0x18002605d`
- name: `?GetMcpServiceType@McpService@@UEAAJPEAW4_McpServiceType@@@Z`
- size: `157`
- prototype: `__int64 __fastcall(CloudPrint::CloudPrintHelper **this, enum _McpServiceType *)`
- caller_count: `0`
- callee_count: `4`
- tags: `service_task`

## callees

- `0x18000c4cc`
- `0x1800195fc`
- `0x18001c298`
- `0x180025fc0`

## string_xrefs

- `0x180025fe2`: `onecoreuap\printscan\print\mcp\managementsvc\lib\mcpservice.cpp`

## pseudocode

```c
__int64 __fastcall McpService::GetMcpServiceType(CloudPrint::CloudPrintHelper **this, enum _McpServiceType *a2)
{
  int v5; // eax
  CloudPrint::CloudPrintHelper *v6; // rcx
  int v7; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  if ( !a2 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2D,
      (unsigned int)"onecoreuap\\printscan\\print\\mcp\\managementsvc\\lib\\mcpservice.cpp",
      (const char *)0x80004003LL,
      v7);
    return 2147500035LL;
  }
  *(_DWORD *)a2 = 0;
  if ( CloudPrint::CloudPrintHelper::IsMps(this[3]) )
  {
    v5 = 1;
LABEL_9:
    *(_DWORD *)a2 = v5;
    return 0;
  }
  v6 = this[3];
  if ( !*((_BYTE *)v6 + 10) )
  {
    if ( *((_BYTE *)v6 + 8) )
    {
      v5 = 2;
      if ( *((_DWORD *)v6 + 3) == 2 )
        goto LABEL_9;
    }
    else
    {
      CloudPrintHelperTelemetry::WriteDbgTraceWarning(
        "CloudPrint::CloudPrintHelper::IsHcp",
        L"Cloud Print Helper is not initialized.");
    }
  }
  return 2147947423LL;
}

```

## disassembly

```asm
0x180025fc0  mov     [rsp+arg_0], rbx
0x180025fc5  push    rdi; int
0x180025fc6  sub     rsp, 20h
0x180025fca  mov     rbx, rdx
0x180025fcd  mov     rdi, rcx
0x180025fd0  test    rdx, rdx
0x180025fd3  jnz     short loc_180025FF7
0x180025fd5  mov     rcx, [rsp+28h]; this
0x180025fda  mov     ebx, 80004003h
0x180025fdf  mov     r9d, ebx; char *
0x180025fe2  lea     r8, aOnecoreuapPrin_7; "onecoreuap\\printscan\\print\\mcp\\mana"...
0x180025fe9  mov     edx, 2Dh ; '-'; void *
0x180025fee  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180025ff3  mov     eax, ebx
0x180025ff5  jmp     short loc_180026051
0x180025ff7  mov     dword ptr [rdx], 0
0x180025ffd  mov     rcx, [rcx+18h]; this
0x180026001  call    ?IsMps@CloudPrintHelper@CloudPrint@@QEBA_NXZ; CloudPrint::CloudPrintHelper::IsMps(void)
0x180026006  test    al, al
0x180026008  jz      short loc_180026011
0x18002600a  mov     eax, 1
0x18002600f  jmp     short loc_180026040
0x180026011  mov     rcx, [rdi+18h]
0x180026015  cmp     byte ptr [rcx+0Ah], 0
0x180026019  jnz     short loc_180026046
0x18002601b  cmp     byte ptr [rcx+8], 0
0x18002601f  jnz     short loc_180026036
0x180026021  lea     rdx, aCloudPrintHelp_0; "Cloud Print Helper is not initialized."
0x180026028  lea     rcx, aCloudprintClou_3; "CloudPrint::CloudPrintHelper::IsHcp"
0x18002602f  call    ?WriteDbgTraceWarning@CloudPrintHelperTelemetry@@SAXPEADPEAGZZ; CloudPrintHelperTelemetry::WriteDbgTraceWarning(char *,ushort *,...)
0x180026034  jmp     short loc_180026046
0x180026036  mov     eax, 2
0x18002603b  cmp     [rcx+0Ch], eax
0x18002603e  jnz     short loc_180026046
0x180026040  mov     [rbx], eax
0x180026042  xor     eax, eax
0x180026044  jmp     short loc_180026051
0x180026046  mov     eax, 8007139Fh
0x18002604b  jmp     short loc_180026051
0x18002604d  mov     eax, [rsp+28h+arg_8]
0x180026051  mov     rbx, [rsp+28h+arg_0]
0x180026056  add     rsp, 20h
0x18002605a  pop     rdi
0x18002605b  retn
```
