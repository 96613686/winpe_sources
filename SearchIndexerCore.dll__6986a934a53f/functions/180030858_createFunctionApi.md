# createFunctionApi

- ea: `0x180030858`
- end: `0x1800309ba`
- name: `createFunctionApi`
- size: `354`
- prototype: `__int64 __fastcall(__int64, int, int, int, __int64, __int64, __int64, __int64, __int64, __int64, void (__fastcall *)(__int64))`
- caller_count: `6`
- callee_count: `11`
- tags: ``

## callers

- `0x180030490`
- `0x180030570`
- `0x180030680`
- `0x1800306e0`
- `0x18009b660`
- `0x1800ae500`

## callees

- `0x180024640`
- `0x1800257e0`
- `0x180027290`
- `0x180030858`
- `0x1800309c0`
- `0x180038d00`
- `0x18003c510`
- `0x18003f840`
- `0x180041eb0`
- `0x18006dc30`
- `0x1800b0010`

## pseudocode

```c
__int64 __fastcall createFunctionApi(
        __int64 a1,
        int a2,
        int a3,
        int a4,
        __int64 a5,
        __int64 a6,
        __int64 a7,
        __int64 a8,
        __int64 a9,
        __int64 a10,
        void (__fastcall *a11)(__int64))
{
  _DWORD *v15; // rbx
  unsigned int Func; // r14d
  unsigned int v17; // ebx
  __int64 v19; // rax

  if ( !(unsigned int)sqlite3SafetyCheckOk(a1) )
  {
    v17 = 21;
    sqlite3_log(
      21,
      "%s at line %d of [%.10s]",
      "misuse",
      182246,
      "18a3cf29885901ce73120761875ccdd0e3704e39307ee4f79d503ddacc55c7af");
    return v17;
  }
  v15 = 0;
  sqlite3_mutex_enter(*(_QWORD *)(a1 + 24));
  if ( !a11 )
    goto LABEL_3;
  v19 = sqlite3Malloc(24);
  v15 = (_DWORD *)v19;
  if ( v19 )
  {
    *(_DWORD *)v19 = 0;
    *(_QWORD *)(v19 + 8) = a11;
    *(_QWORD *)(v19 + 16) = a5;
LABEL_3:
    Func = sqlite3CreateFunc(a1, a2, a3, a4, a5, a6, a7, a8, a9, a10, (__int64)v15);
    if ( v15 && !*v15 )
    {
      a11(a5);
      sqlite3_free(v15);
    }
    goto LABEL_4;
  }
  Func = 1;
  sqlite3OomFault(a1);
  a11(a5);
LABEL_4:
  v17 = sqlite3ApiExit(a1, Func);
  sqlite3_mutex_leave(*(_QWORD *)(a1 + 24));
  return v17;
}

```

## disassembly

```asm
0x180030858  push    rbx
0x18003085a  push    rbp
0x18003085b  push    rsi
0x18003085c  push    rdi
0x18003085d  push    r12
0x18003085f  push    r14
0x180030861  push    r15
0x180030863  sub     rsp, 60h
0x180030867  mov     r14d, r9d
0x18003086a  mov     r15d, r8d
0x18003086d  mov     r12, rdx
0x180030870  mov     rdi, rcx
0x180030873  call    sqlite3SafetyCheckOk
0x180030878  test    eax, eax
0x18003087a  jz      loc_18003096E
0x180030880  mov     rcx, [rdi+18h]
0x180030884  xor     ebx, ebx
0x180030886  call    sqlite3_mutex_enter
0x18003088b  mov     rsi, [rsp+98h+arg_50]
0x180030893  mov     rbp, [rsp+98h+arg_20]
0x18003089b  test    rsi, rsi
0x18003089e  jnz     loc_18003092F
0x1800308a4  mov     rax, [rsp+98h+arg_48]
0x1800308ac  mov     r9d, r14d
0x1800308af  mov     [rsp+98h+var_48], rbx
0x1800308b4  mov     r8d, r15d
0x1800308b7  mov     [rsp+98h+var_50], rax
0x1800308bc  mov     rdx, r12
0x1800308bf  mov     rax, [rsp+98h+arg_40]
0x1800308c7  mov     rcx, rdi
0x1800308ca  mov     [rsp+98h+var_58], rax
0x1800308cf  mov     rax, [rsp+98h+arg_38]
0x1800308d7  mov     [rsp+98h+var_60], rax
0x1800308dc  mov     rax, [rsp+98h+arg_30]
0x1800308e4  mov     [rsp+98h+var_68], rax
0x1800308e9  mov     rax, [rsp+98h+arg_28]
0x1800308f1  mov     [rsp+98h+var_70], rax
0x1800308f6  mov     [rsp+98h+var_78], rbp
0x1800308fb  call    sqlite3CreateFunc
0x180030900  mov     r14d, eax
0x180030903  test    rbx, rbx
0x180030906  jnz     short loc_180030954
0x180030908  mov     edx, r14d
0x18003090b  mov     rcx, rdi
0x18003090e  call    sqlite3ApiExit
0x180030913  mov     rcx, [rdi+18h]
0x180030917  mov     ebx, eax
0x180030919  call    sqlite3_mutex_leave
0x18003091e  mov     eax, ebx
0x180030920  add     rsp, 60h
0x180030924  pop     r15
0x180030926  pop     r14
0x180030928  pop     r12
0x18003092a  pop     rdi
0x18003092b  pop     rsi
0x18003092c  pop     rbp
0x18003092d  pop     rbx
0x18003092e  retn
0x18003092f  mov     ecx, 18h
0x180030934  call    sqlite3Malloc
0x180030939  mov     rbx, rax
0x18003093c  test    rax, rax
0x18003093f  jz      short loc_18003099C
0x180030941  mov     dword ptr [rax], 0
0x180030947  mov     [rax+8], rsi
0x18003094b  mov     [rax+10h], rbp
0x18003094f  jmp     loc_1800308A4
0x180030954  cmp     dword ptr [rbx], 0
0x180030957  jnz     short loc_180030908
0x180030959  mov     rcx, rbp
0x18003095c  mov     rax, rsi
0x18003095f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030964  mov     rcx, rbx
0x180030967  call    sqlite3_free
0x18003096c  jmp     short loc_180030908
0x18003096e  lea     rax, a20240523134606+14h; "18a3cf29885901ce73120761875ccdd0e3704e3"...
0x180030975  mov     ebx, 15h
0x18003097a  mov     ecx, ebx
0x18003097c  mov     [rsp+98h+var_78], rax
0x180030981  mov     r9d, 2C7E6h
0x180030987  lea     r8, aMisuse; "misuse"
0x18003098e  lea     rdx, aSAtLineDOf10s; "%s at line %d of [%.10s]"
0x180030995  call    sqlite3_log
0x18003099a  jmp     short loc_18003091E
0x18003099c  mov     rcx, rdi
0x18003099f  mov     r14d, 1
0x1800309a5  call    sqlite3OomFault
0x1800309aa  mov     rcx, rbp
0x1800309ad  mov     rax, rsi
0x1800309b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800309b5  jmp     loc_180030908
```
