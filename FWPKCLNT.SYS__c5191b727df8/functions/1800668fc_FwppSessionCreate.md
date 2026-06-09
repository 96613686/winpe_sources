# FwppSessionCreate

- ea: `0x1800668fc`
- end: `0x180066a9d`
- name: `FwppSessionCreate`
- size: `417`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: ``

## callers

- `0x180066880`

## callees

- `0x180004904`
- `0x1800050cc`
- `0x180008440`
- `0x18000891c`
- `0x180009850`
- `0x18000c9b4`
- `0x1800203c0`
- `0x1800208c0`
- `0x1800668fc`
- `0x180066aa4`
- `0x180066bd8`
- `0x180066c78`

## import_xrefs

- `ntoskrnl!KeInitializeSemaphore` at `0x180066a7b`
- `ntoskrnl!KeInitializeSemaphore` at `0x180066a7b`

## string_xrefs

- `0x180066a48`: `FwppSessionCreate`
- `0x180066a8c`: `FwppSessionCreate`
- `0x180066a61`: `FwppProxyEngineOpen`

## pseudocode

```c
__int64 __fastcall FwppSessionCreate(__int64 a1, int a2, __int64 a3, int a4, struct _KSEMAPHORE **a5)
{
  int v5; // eax
  __int64 Local; // rbx
  struct _KSEMAPHORE *v8; // rdi
  int v9; // r8d
  int v10; // eax
  __int64 v11; // rcx
  __int64 v13; // rax
  void *v14; // [rsp+30h] [rbp-38h] BYREF
  void *v15; // [rsp+38h] [rbp-30h] BYREF
  __int64 v16; // [rsp+40h] [rbp-28h] BYREF

  v5 = 10;
  v14 = 0;
  if ( a2 != -1 )
    v5 = a2;
  v16 = 0;
  v15 = 0;
  *a5 = 0;
  if ( a1 || v5 != 10 || a3 )
  {
    v13 = WfpReportAppErrorAsNtStatus(a1, (__int64)"FwppSessionCreate", 3221225659LL);
    goto LABEL_16;
  }
  Local = WfpPoolAllocNonPaged(72, 1886418758, &v14);
  if ( Local )
    goto LABEL_11;
  v8 = (struct _KSEMAPHORE *)v14;
  memset(v14, 0, 0x48u);
  Local = FwppRpcBindingCreateLocal((__int64)&unk_180033B30, 0, (RPC_BINDING_HANDLE *)v8);
  if ( Local )
    goto LABEL_11;
  Local = FwppRpcBindingBind(*(RPC_BINDING_HANDLE *)&v8->Header.Lock, &unk_180022030);
  if ( Local )
    goto LABEL_11;
  v10 = FwppProxyEngineOpen(*(_QWORD *)&v8->Header.Lock, a4, v9, (int)v8 + 8, (__int64)&v15, (__int64)&v16);
  if ( v10 < 0 )
  {
    v13 = WfpReportSysErrorAsNtStatus(v11, (int)"FwppProxyEngineOpen", v10);
LABEL_16:
    Local = v13;
    if ( v13 )
      goto LABEL_11;
    goto LABEL_12;
  }
  Local = FwppRpcBindingCreateLocal((__int64)&unk_180033B20, 0, (RPC_BINDING_HANDLE *)&v8->Header.WaitListHead.Blink);
  if ( Local )
  {
LABEL_11:
    FwppSessionDestroy(&v14);
    goto LABEL_12;
  }
  KeInitializeSemaphore(v8 + 1, 1, 1);
  *a5 = v8;
LABEL_12:
  FwppDeepFree_GUID(v15);
  if ( Local )
    WfpReportError(Local, (int)"FwppSessionCreate");
  return Local;
}

```

## disassembly

```asm
0x1800668fc  mov     r11, rsp
0x1800668ff  mov     [r11+8], rbx
0x180066903  push    rbp
0x180066904  push    rsi
0x180066905  push    rdi
0x180066906  sub     rsp, 50h
0x18006690a  mov     rax, cs:__security_cookie
0x180066911  xor     rax, rsp
0x180066914  mov     [rsp+68h+var_20], rax
0x180066919  mov     rsi, [rsp+68h+arg_20]
0x180066921  cmp     edx, 0FFFFFFFFh
0x180066924  mov     eax, 0Ah
0x180066929  mov     qword ptr [r11-38h], 0
0x180066931  cmovnz  eax, edx
0x180066934  mov     qword ptr [r11-28h], 0
0x18006693c  mov     qword ptr [r11-30h], 0
0x180066944  mov     rbp, r9
0x180066947  mov     qword ptr [rsi], 0
0x18006694e  test    rcx, rcx
0x180066951  jnz     loc_180066A42
0x180066957  cmp     eax, 0Ah
0x18006695a  jnz     loc_180066A42
0x180066960  test    r8, r8
0x180066963  jnz     loc_180066A42
0x180066969  lea     edi, [rcx+48h]
0x18006696c  mov     edx, 70707746h
0x180066971  mov     ecx, edi
0x180066973  lea     r8, [r11-38h]
0x180066977  call    WfpPoolAllocNonPaged
0x18006697c  mov     rbx, rax
0x18006697f  test    rax, rax
0x180066982  jnz     loc_180066A0B
0x180066988  mov     r8d, edi; Size
0x18006698b  xor     edx, edx; Val
0x18006698d  mov     rdi, [rsp+68h+var_38]
0x180066992  mov     rcx, rdi; void *
0x180066995  call    memset
0x18006699a  mov     r8, rdi
0x18006699d  lea     rcx, unk_180033B30
0x1800669a4  xor     edx, edx
0x1800669a6  call    FwppRpcBindingCreateLocal
0x1800669ab  mov     rbx, rax
0x1800669ae  test    rax, rax
0x1800669b1  jnz     short loc_180066A0B
0x1800669b3  mov     rcx, [rdi]; Binding
0x1800669b6  lea     rdx, unk_180022030; IfSpec
0x1800669bd  call    FwppRpcBindingBind
0x1800669c2  mov     rbx, rax
0x1800669c5  test    rax, rax
0x1800669c8  jnz     short loc_180066A0B
0x1800669ca  mov     rcx, [rdi]
0x1800669cd  lea     rax, [rsp+68h+var_28]
0x1800669d2  mov     [rsp+68h+var_40], rax
0x1800669d7  lea     r9, [rdi+8]
0x1800669db  lea     rax, [rsp+68h+var_30]
0x1800669e0  mov     rdx, rbp
0x1800669e3  mov     [rsp+68h+var_48], rax
0x1800669e8  call    FwppProxyEngineOpen
0x1800669ed  test    eax, eax
0x1800669ef  js      short loc_180066A5E
0x1800669f1  lea     r8, [rdi+10h]
0x1800669f5  xor     edx, edx
0x1800669f7  lea     rcx, unk_180033B20
0x1800669fe  call    FwppRpcBindingCreateLocal
0x180066a03  mov     rbx, rax
0x180066a06  test    rax, rax
0x180066a09  jz      short loc_180066A6F
0x180066a0b  lea     rcx, [rsp+68h+var_38]
0x180066a10  call    FwppSessionDestroy
0x180066a15  mov     rcx, [rsp+68h+var_30]
0x180066a1a  call    FwppDeepFree_GUID
0x180066a1f  test    rbx, rbx
0x180066a22  jnz     short loc_180066A8C
0x180066a24  mov     rax, rbx
0x180066a27  mov     rcx, [rsp+68h+var_20]
0x180066a2c  xor     rcx, rsp; StackCookie
0x180066a2f  call    __security_check_cookie
0x180066a34  mov     rbx, [rsp+68h+arg_0]
0x180066a39  add     rsp, 50h
0x180066a3d  pop     rdi
0x180066a3e  pop     rsi
0x180066a3f  pop     rbp
0x180066a40  retn
0x180066a42  mov     r8d, 0C00000BBh
0x180066a48  lea     rdx, aFwppsessioncre; "FwppSessionCreate"
0x180066a4f  call    WfpReportAppErrorAsNtStatus
0x180066a54  mov     rbx, rax
0x180066a57  test    rax, rax
0x180066a5a  jz      short loc_180066A15
0x180066a5c  jmp     short loc_180066A0B
0x180066a5e  mov     r8d, eax
0x180066a61  lea     rdx, aFwppproxyengin_1; "FwppProxyEngineOpen"
0x180066a68  call    WfpReportSysErrorAsNtStatus
0x180066a6d  jmp     short loc_180066A54
0x180066a6f  mov     edx, 1; Count
0x180066a74  lea     rcx, [rdi+20h]; Semaphore
0x180066a78  mov     r8d, edx; Limit
0x180066a7b  call    cs:__imp_KeInitializeSemaphore
0x180066a82  nop     dword ptr [rax+rax+00h]
0x180066a87  mov     [rsi], rdi
0x180066a8a  jmp     short loc_180066A15
0x180066a8c  lea     rdx, aFwppsessioncre; "FwppSessionCreate"
0x180066a93  mov     rcx, rbx
0x180066a96  call    WfpReportError
0x180066a9b  jmp     short loc_180066A24
```
