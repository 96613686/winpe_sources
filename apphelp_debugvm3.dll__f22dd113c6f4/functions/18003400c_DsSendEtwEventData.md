# DsSendEtwEventData

- ea: `0x18003400c`
- end: `0x1800340dc`
- name: `DsSendEtwEventData`
- size: `208`
- prototype: ``
- caller_count: `10`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18002eac0`
- `0x18002ece0`
- `0x18002f0f0`
- `0x180032600`
- `0x180055840`
- `0x1800559a0`
- `0x180055ae0`
- `0x180055bd0`
- `0x180055cc0`
- `0x180055ec0`

## callees

- `0x18001c320`
- `0x1800591b0`

## import_xrefs

- `ntdll!EtwEventWriteNoRegistration` at `0x18003408f`
- `ntdll!EtwEventWriteNoRegistration` at `0x18003408f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800340b5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800340b5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003403f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003403f`

## pseudocode

```c
void __fastcall DsSendEtwEventData(__int64 a1, __int64 a2, int a3)
{
  DWORD LastError; // esi
  int v6; // [rsp+20h] [rbp-40h] BYREF
  _QWORD v7[5]; // [rsp+28h] [rbp-38h] BYREF
  int v8; // [rsp+50h] [rbp-10h]
  int v9; // [rsp+54h] [rbp-Ch]

  v6 = a3;
  LastError = GetLastError();
  v7[1] = 4;
  v7[3] = 4;
  v7[0] = &dword_180081310;
  v7[4] = a2;
  v7[2] = &v6;
  v8 = v6;
  v9 = 0;
  EtwEventWriteNoRegistration(AE_LOG, a1, 3, v7);
  DsTracePrintf("DetectorShims,Fired,%d,%x");
  ++qword_180081308;
  SetLastError(LastError);
}

```

## disassembly

```asm
0x18003400c  mov     [rsp-18h+arg_8], rbx
0x180034011  mov     [rsp-18h+arg_10], rsi
0x180034016  push    rbp
0x180034017  push    rdi
0x180034018  push    r14
0x18003401a  mov     rbp, rsp
0x18003401d  sub     rsp, 60h
0x180034021  mov     rax, cs:__security_cookie
0x180034028  xor     rax, rsp
0x18003402b  mov     [rbp+var_8], rax
0x18003402f  mov     rdi, r8
0x180034032  mov     [rbp+var_40], 0
0x180034039  mov     rbx, rdx
0x18003403c  mov     r14, rcx
0x18003403f  call    cs:__imp_GetLastError
0x180034045  lea     r9, [rbp+var_38]
0x180034049  mov     [rbp+var_40], edi
0x18003404c  mov     esi, eax
0x18003404e  mov     [rbp+var_30], 4
0x180034056  lea     rax, dword_180081310
0x18003405d  mov     [rbp+var_20], 4
0x180034065  mov     [rbp+var_38], rax
0x180034069  lea     rcx, AE_LOG
0x180034070  lea     rax, [rbp+var_40]
0x180034074  mov     [rbp+var_18], rbx
0x180034078  mov     r8d, 3
0x18003407e  mov     [rbp+var_28], rax
0x180034082  mov     rdx, r14
0x180034085  mov     [rbp+var_10], edi
0x180034088  mov     [rbp+var_C], 0
0x18003408f  call    cs:__imp_EtwEventWriteNoRegistration
0x180034095  movzx   edx, word ptr [r14]
0x180034099  lea     rcx, aDetectorshimsF; "DetectorShims,Fired,%d,%x"
0x1800340a0  mov     r8d, cs:dword_180081310
0x1800340a7  call    DsTracePrintf
0x1800340ac  inc     cs:qword_180081308
0x1800340b3  mov     ecx, esi; dwErrCode
0x1800340b5  call    cs:__imp_SetLastError
0x1800340bb  mov     rcx, [rbp+var_8]
0x1800340bf  xor     rcx, rsp; StackCookie
0x1800340c2  call    __security_check_cookie
0x1800340c7  lea     r11, [rsp+60h+var_s0]
0x1800340cc  mov     rbx, [r11+28h]
0x1800340d0  mov     rsi, [r11+30h]
0x1800340d4  mov     rsp, r11
0x1800340d7  pop     r14
0x1800340d9  pop     rdi
0x1800340da  pop     rbp
0x1800340db  retn
```
