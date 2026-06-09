# UpdateRegistryValues

- ea: `0x1800070d0`
- end: `0x180007134`
- name: `UpdateRegistryValues`
- size: `100`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x180005b28`
- `0x18000683c`
- `0x1800070d0`
- `0x180011010`

## pseudocode

```c
__int64 __fastcall UpdateRegistryValues(unsigned int a1)
{
  int inited; // ebx
  __int64 v3; // rdx
  int v5; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  inited = InitMicDiagnostic();
  if ( inited < 0 )
  {
    v3 = 181;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v3,
      (unsigned int)"base\\diagnosis\\pdi\\scripteddiag\\packages\\speech\\speechdiagnosticutil\\speechdiagnosticutil.cpp",
      (const char *)(unsigned int)inited,
      v5);
    return (unsigned int)inited;
  }
  inited = (*(__int64 (__fastcall **)(struct SpeechMicDiagnostic::ISpeechMicDiagnostic *, _QWORD))(*(_QWORD *)g_pSpeechDiagnostic
                                                                                                 + 64LL))(
             g_pSpeechDiagnostic,
             a1);
  if ( inited < 0 )
  {
    v3 = 182;
    goto LABEL_3;
  }
  return 0;
}

```

## disassembly

```asm
0x1800070d0  mov     [rsp+arg_0], rbx
0x1800070d5  push    rdi; int
0x1800070d6  sub     rsp, 20h
0x1800070da  mov     edi, ecx
0x1800070dc  call    ?InitMicDiagnostic@@YAJXZ; InitMicDiagnostic(void)
0x1800070e1  mov     ebx, eax
0x1800070e3  test    eax, eax
0x1800070e5  jns     short loc_180007104
0x1800070e7  mov     edx, 0B5h; void *
0x1800070ec  mov     rcx, [rsp+28h]; this
0x1800070f1  lea     r8, aBaseDiagnosisP; "base\\diagnosis\\pdi\\scripteddiag\\pac"...
0x1800070f8  mov     r9d, ebx; char *
0x1800070fb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180007100  mov     eax, ebx
0x180007102  jmp     short loc_180007128
0x180007104  mov     rcx, cs:?g_pSpeechDiagnostic@@3PEAUISpeechMicDiagnostic@SpeechMicDiagnostic@@EA; SpeechMicDiagnostic::ISpeechMicDiagnostic * g_pSpeechDiagnostic
0x18000710b  mov     edx, edi
0x18000710d  mov     rax, [rcx]
0x180007110  mov     rax, [rax+40h]
0x180007114  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007119  mov     ebx, eax
0x18000711b  test    eax, eax
0x18000711d  jns     short loc_180007126
0x18000711f  mov     edx, 0B6h
0x180007124  jmp     short loc_1800070EC
0x180007126  xor     eax, eax
0x180007128  mov     rbx, [rsp+28h+arg_0]
0x18000712d  add     rsp, 20h
0x180007131  pop     rdi
0x180007132  retn
```
