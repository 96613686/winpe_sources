# Deinitialize

- ea: `0x180030970`
- end: `0x180030aa5`
- name: `Deinitialize`
- size: `309`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180021f70`
- `0x180030970`
- `0x18006a010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x1800309be`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x1800309be`
- `KERNEL32!GetCurrentThreadId` at `0x180030996`
- `KERNEL32!GetCurrentThreadId` at `0x180030996`
- `KERNEL32!LeaveCriticalSection` at `0x180030a96`
- `KERNEL32!LeaveCriticalSection` at `0x180030a96`
- `KERNEL32!EnterCriticalSection` at `0x18003097d`
- `KERNEL32!EnterCriticalSection` at `0x18003097d`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 Deinitialize()
{
  int v0; // eax
  char *v1; // rax
  const char *v2; // rax
  __int64 v3; // rbx
  volatile signed __int32 *v4; // rbx

  EnterCriticalSection(&CriticalSection);
  v0 = qword_1800AA688 + 1;
  LODWORD(qword_1800AA688) = v0;
  if ( v0 == 1 )
  {
    HIDWORD(qword_1800AA688) = GetCurrentThreadId();
    v0 = qword_1800AA688;
  }
  if ( qword_1800AA8A0 )
  {
    v4 = (volatile signed __int32 *)qword_1800AA8A8;
    qword_1800AA8A0 = 0;
    qword_1800AA8A8 = 0;
    if ( v4 )
    {
      if ( _InterlockedExchangeAdd(v4 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v4)(v4);
        if ( _InterlockedExchangeAdd(v4 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v4 + 8LL))(v4);
      }
      v0 = qword_1800AA688;
    }
    LODWORD(qword_1800AA688) = v0 - 1;
    if ( v0 == 1 )
      qword_1800AA688 = 0;
    v3 = 0x8000000000LL;
  }
  else
  {
    v1 = strrchr("admin\\appman\\appv\\client\\streaming\\interface.cpp", 92);
    if ( v1 )
      v2 = v1 + 1;
    else
      v2 = "admin\\appman\\appv\\client\\streaming\\interface.cpp";
    v3 = (sub_180021F70(&qword_1800AA650, v2) << 52) | 0xB0C00000003LL;
    LODWORD(qword_1800AA688) = qword_1800AA688 - 1;
    if ( !(_DWORD)qword_1800AA688 )
      qword_1800AA688 = 0;
  }
  LeaveCriticalSection(&CriticalSection);
  return v3;
}

```

## disassembly

```asm
0x180030970  push    rbx
0x180030972  sub     rsp, 20h
0x180030976  lea     rcx, CriticalSection; lpCriticalSection
0x18003097d  call    cs:EnterCriticalSection
0x180030983  mov     eax, dword ptr cs:qword_1800AA688
0x180030989  inc     eax
0x18003098b  mov     dword ptr cs:qword_1800AA688, eax
0x180030991  cmp     eax, 1
0x180030994  jnz     short loc_1800309A8
0x180030996  call    cs:GetCurrentThreadId
0x18003099c  mov     dword ptr cs:qword_1800AA688+4, eax
0x1800309a2  mov     eax, dword ptr cs:qword_1800AA688
0x1800309a8  cmp     cs:qword_1800AA8A0, 0
0x1800309b0  jnz     short loc_180030A11
0x1800309b2  mov     edx, 5Ch ; '\'; Ch
0x1800309b7  lea     rcx, aAdminAppmanApp_3; "admin\\appman\\appv\\client\\streaming"...
0x1800309be  call    cs:strrchr
0x1800309c4  test    rax, rax
0x1800309c7  jz      short loc_1800309CE
0x1800309c9  inc     rax
0x1800309cc  jmp     short loc_1800309D5
0x1800309ce  lea     rax, aAdminAppmanApp_3; "admin\\appman\\appv\\client\\streaming"...
0x1800309d5  mov     rdx, rax
0x1800309d8  lea     rcx, qword_1800AA650
0x1800309df  call    sub_180021F70
0x1800309e4  mov     rbx, rax
0x1800309e7  mov     rax, 0B0C00000003h
0x1800309f1  shl     rbx, 34h
0x1800309f5  or      rbx, rax
0x1800309f8  sub     dword ptr cs:qword_1800AA688, 1
0x1800309ff  jnz     loc_180030A8F
0x180030a05  mov     dword ptr cs:qword_1800AA688+4, 0
0x180030a0f  jmp     short loc_180030A8F
0x180030a11  mov     rbx, cs:qword_1800AA8A8
0x180030a18  mov     cs:qword_1800AA8A0, 0
0x180030a23  mov     cs:qword_1800AA8A8, 0
0x180030a2e  test    rbx, rbx
0x180030a31  jz      short loc_180030A70
0x180030a33  or      eax, 0FFFFFFFFh
0x180030a36  lock xadd [rbx+8], eax
0x180030a3b  cmp     eax, 1
0x180030a3e  jnz     short loc_180030A6A
0x180030a40  mov     rax, [rbx]
0x180030a43  mov     rcx, rbx
0x180030a46  mov     rax, [rax]
0x180030a49  call    j__guard_dispatch_icall
0x180030a4e  or      eax, 0FFFFFFFFh
0x180030a51  lock xadd [rbx+0Ch], eax
0x180030a56  cmp     eax, 1
0x180030a59  jnz     short loc_180030A6A
0x180030a5b  mov     rax, [rbx]
0x180030a5e  mov     rcx, rbx
0x180030a61  mov     rax, [rax+8]
0x180030a65  call    j__guard_dispatch_icall
0x180030a6a  mov     eax, dword ptr cs:qword_1800AA688
0x180030a70  sub     eax, 1
0x180030a73  mov     dword ptr cs:qword_1800AA688, eax
0x180030a79  jnz     short loc_180030A85
0x180030a7b  mov     dword ptr cs:qword_1800AA688+4, 0
0x180030a85  mov     rbx, 8000000000h
0x180030a8f  lea     rcx, CriticalSection; lpCriticalSection
0x180030a96  call    cs:LeaveCriticalSection
0x180030a9c  mov     rax, rbx
0x180030a9f  add     rsp, 20h
0x180030aa3  pop     rbx
0x180030aa4  retn
```
