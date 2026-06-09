# GetComponent

- ea: `0x180030ab0`
- end: `0x180030b80`
- name: `GetComponent`
- size: `208`
- prototype: `__int64 __fastcall(_QWORD *)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180021f70`
- `0x180030ab0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x180030afb`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x180030afb`
- `KERNEL32!GetCurrentThreadId` at `0x180030ad9`
- `KERNEL32!GetCurrentThreadId` at `0x180030ad9`
- `KERNEL32!LeaveCriticalSection` at `0x180030b71`
- `KERNEL32!LeaveCriticalSection` at `0x180030b71`
- `KERNEL32!EnterCriticalSection` at `0x180030ac0`
- `KERNEL32!EnterCriticalSection` at `0x180030ac0`

## pseudocode

```c
__int64 __fastcall GetComponent(_QWORD *a1)
{
  char *v2; // rax
  const char *v3; // rax
  __int64 v4; // rbx

  EnterCriticalSection(&CriticalSection);
  LODWORD(qword_1800AA688) = qword_1800AA688 + 1;
  if ( (_DWORD)qword_1800AA688 == 1 )
    HIDWORD(qword_1800AA688) = GetCurrentThreadId();
  if ( qword_1800AA8A0 )
  {
    *a1 = qword_1800AA8A0;
    LODWORD(qword_1800AA688) = qword_1800AA688 - 1;
    if ( !(_DWORD)qword_1800AA688 )
      qword_1800AA688 = 0;
    v4 = 0x8000000000LL;
  }
  else
  {
    v2 = strrchr("admin\\appman\\appv\\client\\streaming\\interface.cpp", 92);
    if ( v2 )
      v3 = v2 + 1;
    else
      v3 = "admin\\appman\\appv\\client\\streaming\\interface.cpp";
    v4 = (sub_180021F70(&qword_1800AA650, v3) << 52) | 0xD0C00000003LL;
    LODWORD(qword_1800AA688) = qword_1800AA688 - 1;
    if ( !(_DWORD)qword_1800AA688 )
      qword_1800AA688 = 0;
  }
  LeaveCriticalSection(&CriticalSection);
  return v4;
}

```

## disassembly

```asm
0x180030ab0  push    rbx
0x180030ab2  sub     rsp, 20h
0x180030ab6  mov     rbx, rcx
0x180030ab9  lea     rcx, CriticalSection; lpCriticalSection
0x180030ac0  call    cs:EnterCriticalSection
0x180030ac6  mov     eax, dword ptr cs:qword_1800AA688
0x180030acc  inc     eax
0x180030ace  mov     dword ptr cs:qword_1800AA688, eax
0x180030ad4  cmp     eax, 1
0x180030ad7  jnz     short loc_180030AE5
0x180030ad9  call    cs:GetCurrentThreadId
0x180030adf  mov     dword ptr cs:qword_1800AA688+4, eax
0x180030ae5  mov     rax, cs:qword_1800AA8A0
0x180030aec  test    rax, rax
0x180030aef  jnz     short loc_180030B4A
0x180030af1  lea     edx, [rax+5Ch]; Ch
0x180030af4  lea     rcx, aAdminAppmanApp_3; "admin\\appman\\appv\\client\\streaming"...
0x180030afb  call    cs:strrchr
0x180030b01  test    rax, rax
0x180030b04  jz      short loc_180030B0B
0x180030b06  inc     rax
0x180030b09  jmp     short loc_180030B12
0x180030b0b  lea     rax, aAdminAppmanApp_3; "admin\\appman\\appv\\client\\streaming"...
0x180030b12  mov     rdx, rax
0x180030b15  lea     rcx, qword_1800AA650
0x180030b1c  call    sub_180021F70
0x180030b21  mov     rbx, rax
0x180030b24  mov     rax, 0D0C00000003h
0x180030b2e  shl     rbx, 34h
0x180030b32  or      rbx, rax
0x180030b35  sub     dword ptr cs:qword_1800AA688, 1
0x180030b3c  jnz     short loc_180030B6A
0x180030b3e  mov     dword ptr cs:qword_1800AA688+4, 0
0x180030b48  jmp     short loc_180030B6A
0x180030b4a  mov     [rbx], rax
0x180030b4d  sub     dword ptr cs:qword_1800AA688, 1
0x180030b54  jnz     short loc_180030B60
0x180030b56  mov     dword ptr cs:qword_1800AA688+4, 0
0x180030b60  mov     rbx, 8000000000h
0x180030b6a  lea     rcx, CriticalSection; lpCriticalSection
0x180030b71  call    cs:LeaveCriticalSection
0x180030b77  mov     rax, rbx
0x180030b7a  add     rsp, 20h
0x180030b7e  pop     rbx
0x180030b7f  retn
```
