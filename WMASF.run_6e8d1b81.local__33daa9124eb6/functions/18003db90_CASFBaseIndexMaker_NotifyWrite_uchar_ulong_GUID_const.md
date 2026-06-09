# CASFBaseIndexMaker::NotifyWrite(uchar *,ulong,_GUID const &)

- ea: `0x18003db90`
- end: `0x18003dc41`
- name: `?NotifyWrite@CASFBaseIndexMaker@@UEAAJPEAEKAEBU_GUID@@@Z`
- size: `177`
- prototype: `__int64 __fastcall(CASFBaseIndexMaker *__hidden this, unsigned __int8 *, unsigned int, const struct _GUID *)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x1800021dc`
- `0x18000220c`
- `0x18003db90`
- `0x180040010`

## pseudocode

```c
__int64 __fastcall CASFBaseIndexMaker::NotifyWrite(
        struct IWMSCriticalSection **this,
        unsigned __int8 *a2,
        unsigned int a3,
        const struct _GUID *a4)
{
  __int64 v8; // rax
  char v10; // [rsp+60h] [rbp+8h] BYREF

  CAutoCritSec::CAutoCritSec((CAutoCritSec *)&v10, this[1625]);
  if ( *((_DWORD *)this + 3) || !*((_DWORD *)this + 4) )
  {
    CAutoCritSec::~CAutoCritSec((CAutoCritSec *)&v10);
    return 1;
  }
  else
  {
    v8 = *(_QWORD *)&CLSID_ASFDataUnitData.Data1 - *(_QWORD *)&a4->Data1;
    if ( *(_QWORD *)&CLSID_ASFDataUnitData.Data1 == *(_QWORD *)&a4->Data1 )
      v8 = *(_QWORD *)CLSID_ASFDataUnitData.Data4 - *(_QWORD *)a4->Data4;
    if ( !v8 && *((_DWORD *)this + 17) == 2 )
      (*((void (__fastcall **)(char *, unsigned __int8 *, _QWORD, const struct _GUID *, _WORD, _QWORD))*(this - 1) + 13))(
        (char *)this - 8,
        a2,
        a3,
        a4,
        0,
        0);
    CAutoCritSec::~CAutoCritSec((CAutoCritSec *)&v10);
    return 0;
  }
}

```

## disassembly

```asm
0x18003db90  mov     [rsp+arg_8], rbx
0x18003db95  mov     [rsp+arg_10], rbp
0x18003db9a  push    rsi
0x18003db9b  push    rdi
0x18003db9c  push    r14
0x18003db9e  sub     rsp, 40h
0x18003dba2  mov     r14, rdx
0x18003dba5  mov     rbx, rcx
0x18003dba8  mov     rdx, [rcx+32C8h]; struct IWMSCriticalSection *
0x18003dbaf  mov     rdi, r9
0x18003dbb2  lea     rcx, [rsp+58h+arg_0]; this
0x18003dbb7  mov     ebp, r8d
0x18003dbba  call    ??0CAutoCritSec@@QEAA@PEAUIWMSCriticalSection@@@Z; CAutoCritSec::CAutoCritSec(IWMSCriticalSection *)
0x18003dbbf  xor     ecx, ecx
0x18003dbc1  cmp     [rbx+0Ch], ecx
0x18003dbc4  jnz     short loc_18003DC1F
0x18003dbc6  cmp     [rbx+10h], ecx
0x18003dbc9  jz      short loc_18003DC1F
0x18003dbcb  mov     rax, qword ptr cs:CLSID_ASFDataUnitData.Data1
0x18003dbd2  sub     rax, [rdi]
0x18003dbd5  jnz     short loc_18003DBE2
0x18003dbd7  mov     rax, qword ptr cs:CLSID_ASFDataUnitData.Data4
0x18003dbde  sub     rax, [rdi+8]
0x18003dbe2  test    rax, rax
0x18003dbe5  jnz     short loc_18003DC11
0x18003dbe7  cmp     dword ptr [rbx+44h], 2
0x18003dbeb  jnz     short loc_18003DC11
0x18003dbed  mov     rax, [rbx-8]
0x18003dbf1  mov     r9, rdi
0x18003dbf4  mov     [rsp+58h+var_30], rcx
0x18003dbf9  mov     r8d, ebp
0x18003dbfc  mov     [rsp+58h+var_38], cx
0x18003dc01  mov     rdx, r14
0x18003dc04  lea     rcx, [rbx-8]
0x18003dc08  mov     rax, [rax+68h]
0x18003dc0c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003dc11  lea     rcx, [rsp+58h+arg_0]; this
0x18003dc16  call    ??1CAutoCritSec@@QEAA@XZ; CAutoCritSec::~CAutoCritSec(void)
0x18003dc1b  xor     eax, eax
0x18003dc1d  jmp     short loc_18003DC2E
0x18003dc1f  lea     rcx, [rsp+58h+arg_0]; this
0x18003dc24  call    ??1CAutoCritSec@@QEAA@XZ; CAutoCritSec::~CAutoCritSec(void)
0x18003dc29  mov     eax, 1
0x18003dc2e  mov     rbx, [rsp+58h+arg_8]
0x18003dc33  mov     rbp, [rsp+58h+arg_10]
0x18003dc38  add     rsp, 40h
0x18003dc3c  pop     r14
0x18003dc3e  pop     rdi
0x18003dc3f  pop     rsi
0x18003dc40  retn
```
