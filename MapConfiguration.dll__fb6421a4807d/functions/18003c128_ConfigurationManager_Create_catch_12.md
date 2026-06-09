# ConfigurationManager_Create$catch$12

- ea: `0x18003c128`
- end: `0x18003c161`
- name: `ConfigurationManager_Create$catch$12`
- size: `57`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config`

## import_xrefs

- `ZTrace_Maps!ZTraceReportOriginationNoThis` at `0x18003c147`
- `ZTrace_Maps!ZTraceReportOriginationNoThis` at `0x18003c147`

## string_xrefs

- `0x18003c13b`: `ConfigurationManager_Create`

## pseudocode

```c
__int64 __fastcall ConfigurationManager_Create_catch_12(__int64 a1, __int64 a2)
{
  *(_DWORD *)(a2 + 64) = ZTraceReportOriginationNoThis(-2147418113, "ConfigurationManager_Create", 81);
  return 0;
}

```

## disassembly

```asm
0x18003c128  mov     [rsp+arg_8], rdx
0x18003c12d  push    rbp
0x18003c12e  sub     rsp, 20h
0x18003c132  mov     rbp, rdx
0x18003c135  mov     r8d, 51h ; 'Q'
0x18003c13b  lea     rdx, aConfigurationm_5; "ConfigurationManager_Create"
0x18003c142  mov     ecx, 8000FFFFh
0x18003c147  call    cs:__imp_?ZTraceReportOriginationNoThis@@YAJHPEBDH@Z; ZTraceReportOriginationNoThis(int,char const *,int)
0x18003c14d  mov     [rbp+40h], eax
0x18003c150  mov     rax, 0
0x18003c15a  add     rsp, 20h
0x18003c15e  pop     rbp
0x18003c15f  retn
```
