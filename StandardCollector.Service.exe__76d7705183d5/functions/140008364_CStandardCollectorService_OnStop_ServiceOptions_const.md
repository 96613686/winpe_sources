# CStandardCollectorService::OnStop(ServiceOptions const &)

- ea: `0x140008364`
- end: `0x140008432`
- name: `?OnStop@CStandardCollectorService@@AEAAJAEBUServiceOptions@@@Z`
- size: `206`
- prototype: `__int64 __fastcall(CStandardCollectorService *__hidden this, const struct ServiceOptions *)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x140007da0`

## callees

- `0x140008364`
- `0x140014c70`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1400083f2`
- `KERNEL32!GetLastError` at `0x1400083f2`
- `ole32!CoRevokeClassObject` at `0x14000837d`
- `ole32!CoRevokeClassObject` at `0x1400083b1`
- `ole32!CoRevokeClassObject` at `0x14000837d`
- `ole32!CoRevokeClassObject` at `0x1400083b1`
- `ADVAPI32!SetServiceStatus` at `0x1400083e8`
- `ADVAPI32!SetServiceStatus` at `0x14000841b`
- `ADVAPI32!SetServiceStatus` at `0x1400083e8`
- `ADVAPI32!SetServiceStatus` at `0x14000841b`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
int __fastcall CStandardCollectorService::OnStop(CStandardCollectorService *this, const struct ServiceOptions *a2)
{
  int result; // eax
  __int64 v4; // rcx
  __int64 v5; // rcx
  signed int LastError; // ecx

  if ( *(_DWORD *)a2 != 5 )
    return 0;
  result = CoRevokeClassObject(*((_DWORD *)this + 9));
  if ( result < 0 )
    goto LABEL_3;
  v4 = *((_QWORD *)this + 8);
  if ( v4 )
  {
    *((_QWORD *)this + 8) = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
  }
  result = CoRevokeClassObject(*((_DWORD *)this + 10));
  if ( result < 0 )
  {
LABEL_3:
    _mm_lfence();
    return result;
  }
  v5 = *((_QWORD *)this + 9);
  if ( v5 )
  {
    *((_QWORD *)this + 9) = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
  }
  *((_DWORD *)this + 3) = 3;
  if ( SetServiceStatus(*(SERVICE_STATUS_HANDLE *)this, (LPSERVICE_STATUS)((char *)this + 8)) )
  {
    *((_DWORD *)this + 4) &= 0xFFFFFFFA;
    *((_DWORD *)this + 3) = 1;
    if ( SetServiceStatus(*(SERVICE_STATUS_HANDLE *)this, (LPSERVICE_STATUS)((char *)this + 8)) )
      return 0;
  }
  LastError = GetLastError();
  result = (unsigned __int16)LastError | 0x80070000;
  if ( LastError <= 0 )
    return LastError;
  return result;
}

```

## disassembly

```asm
0x140008364  mov     [rsp+arg_0], rbx
0x140008369  push    rdi
0x14000836a  sub     rsp, 20h
0x14000836e  mov     rbx, rcx
0x140008371  cmp     dword ptr [rdx], 5
0x140008374  jnz     loc_140008425
0x14000837a  mov     ecx, [rcx+24h]; dwRegister
0x14000837d  call    cs:__imp_CoRevokeClassObject
0x140008383  test    eax, eax
0x140008385  jns     short loc_14000838F
0x140008387  lfence
0x14000838a  jmp     loc_140008427
0x14000838f  mov     rcx, [rbx+40h]
0x140008393  test    rcx, rcx
0x140008396  jz      short loc_1400083AE
0x140008398  mov     qword ptr [rbx+40h], 0
0x1400083a0  mov     rax, [rcx]
0x1400083a3  mov     rax, [rax+10h]
0x1400083a7  call    cs:__guard_dispatch_icall_fptr
0x1400083ad  nop
0x1400083ae  mov     ecx, [rbx+28h]; dwRegister
0x1400083b1  call    cs:__imp_CoRevokeClassObject
0x1400083b7  test    eax, eax
0x1400083b9  js      short loc_140008387
0x1400083bb  mov     rcx, [rbx+48h]
0x1400083bf  test    rcx, rcx
0x1400083c2  jz      short loc_1400083DA
0x1400083c4  mov     qword ptr [rbx+48h], 0
0x1400083cc  mov     rax, [rcx]
0x1400083cf  mov     rax, [rax+10h]
0x1400083d3  call    cs:__guard_dispatch_icall_fptr
0x1400083d9  nop
0x1400083da  mov     dword ptr [rbx+0Ch], 3
0x1400083e1  lea     rdx, [rbx+8]; lpServiceStatus
0x1400083e5  mov     rcx, [rbx]; hServiceStatus
0x1400083e8  call    cs:__imp_SetServiceStatus
0x1400083ee  test    eax, eax
0x1400083f0  jnz     short loc_140008409
0x1400083f2  call    cs:__imp_GetLastError
0x1400083f8  mov     ecx, eax
0x1400083fa  movzx   eax, ax
0x1400083fd  or      eax, 80070000h
0x140008402  test    ecx, ecx
0x140008404  cmovle  eax, ecx
0x140008407  jmp     short loc_140008427
0x140008409  and     dword ptr [rbx+10h], 0FFFFFFFAh
0x14000840d  mov     dword ptr [rbx+0Ch], 1
0x140008414  lea     rdx, [rbx+8]; lpServiceStatus
0x140008418  mov     rcx, [rbx]; hServiceStatus
0x14000841b  call    cs:__imp_SetServiceStatus
0x140008421  test    eax, eax
0x140008423  jz      short loc_1400083F2
0x140008425  xor     eax, eax
0x140008427  mov     rbx, [rsp+28h+arg_0]
0x14000842c  add     rsp, 20h
0x140008430  pop     rdi
0x140008431  retn
```
