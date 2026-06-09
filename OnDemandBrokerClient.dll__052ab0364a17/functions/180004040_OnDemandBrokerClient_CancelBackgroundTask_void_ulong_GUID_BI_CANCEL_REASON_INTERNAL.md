# OnDemandBrokerClient::CancelBackgroundTask(void *,ulong,_GUID,_BI_CANCEL_REASON_INTERNAL)

- ea: `0x180004040`
- end: `0x1800040cf`
- name: `?CancelBackgroundTask@OnDemandBrokerClient@@UEAAJPEAXKU_GUID@@W4_BI_CANCEL_REASON_INTERNAL@@@Z`
- size: `143`
- prototype: `__int64 __fastcall(__int64, __int64, unsigned int, _OWORD *, int)`
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x180004040`
- `0x180007010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000409d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000409d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000405e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000405e`

## pseudocode

```c
__int64 __fastcall OnDemandBrokerClient::CancelBackgroundTask(
        __int64 a1,
        __int64 a2,
        unsigned int a3,
        _OWORD *a4,
        int a5)
{
  struct _RTL_CRITICAL_SECTION *v5; // rdi
  __int64 *v10; // rcx
  __int64 v11; // rax
  unsigned int v12; // eax
  unsigned int v13; // ebx
  _OWORD v15[3]; // [rsp+40h] [rbp-38h] BYREF

  v5 = (struct _RTL_CRITICAL_SECTION *)(a1 + 24);
  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 24));
  v10 = *(__int64 **)(a1 + 80);
  v11 = *v10;
  v15[0] = *a4;
  if ( a2 )
    v12 = (*(__int64 (__fastcall **)(__int64 *, __int64, _QWORD, _OWORD *, _BYTE, int))(v11 + 80))(
            v10,
            a2,
            a3,
            v15,
            0,
            a5);
  else
    v12 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, _OWORD *, _QWORD, int))(v11 + 72))(v10, a3, v15, 0, a5);
  v13 = v12;
  LeaveCriticalSection(v5);
  return v13;
}

```

## disassembly

```asm
0x180004040  push    rbx
0x180004042  push    rbp
0x180004043  push    rsi
0x180004044  push    rdi
0x180004045  push    r14
0x180004047  sub     rsp, 50h
0x18000404b  lea     rdi, [rcx+18h]
0x18000404f  mov     rbx, rcx
0x180004052  mov     rcx, rdi; lpCriticalSection
0x180004055  mov     rbp, r9
0x180004058  mov     r14d, r8d
0x18000405b  mov     rsi, rdx
0x18000405e  call    cs:__imp_EnterCriticalSection
0x180004064  mov     rcx, [rbx+50h]
0x180004068  mov     edx, [rsp+78h+arg_20]
0x18000406f  movups  xmm0, xmmword ptr [rbp+0]
0x180004073  mov     rax, [rcx]
0x180004076  movaps  [rsp+78h+var_38], xmm0
0x18000407b  test    rsi, rsi
0x18000407e  jnz     short loc_1800040B0
0x180004080  mov     rax, [rax+48h]
0x180004084  lea     r8, [rsp+78h+var_38]
0x180004089  mov     [rsp+78h+var_58], edx
0x18000408d  xor     r9d, r9d
0x180004090  mov     edx, r14d
0x180004093  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004098  mov     rcx, rdi; lpCriticalSection
0x18000409b  mov     ebx, eax
0x18000409d  call    cs:__imp_LeaveCriticalSection
0x1800040a3  mov     eax, ebx
0x1800040a5  add     rsp, 50h
0x1800040a9  pop     r14
0x1800040ab  pop     rdi
0x1800040ac  pop     rsi
0x1800040ad  pop     rbp
0x1800040ae  pop     rbx
0x1800040af  retn
0x1800040b0  mov     rax, [rax+50h]
0x1800040b4  lea     r9, [rsp+78h+var_38]
0x1800040b9  mov     [rsp+78h+var_50], edx
0x1800040bd  mov     r8d, r14d
0x1800040c0  mov     rdx, rsi
0x1800040c3  mov     byte ptr [rsp+78h+var_58], 0
0x1800040c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800040cd  jmp     short loc_180004098
```
