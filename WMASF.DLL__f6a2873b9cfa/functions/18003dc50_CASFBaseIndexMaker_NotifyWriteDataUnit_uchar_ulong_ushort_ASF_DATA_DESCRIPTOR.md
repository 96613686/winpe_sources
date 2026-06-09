# CASFBaseIndexMaker::NotifyWriteDataUnit(uchar *,ulong,ushort,_ASF_DATA_DESCRIPTOR *)

- ea: `0x18003dc50`
- end: `0x18003dcf2`
- name: `?NotifyWriteDataUnit@CASFBaseIndexMaker@@UEAAJPEAEKGPEAU_ASF_DATA_DESCRIPTOR@@@Z`
- size: `162`
- prototype: `__int64 __fastcall(CASFBaseIndexMaker *__hidden this, unsigned __int8 *, unsigned int, unsigned __int16, struct _ASF_DATA_DESCRIPTOR *)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x1800021dc`
- `0x18000220c`
- `0x18003dc50`
- `0x180040010`

## pseudocode

```c
__int64 __fastcall CASFBaseIndexMaker::NotifyWriteDataUnit(
        struct IWMSCriticalSection **this,
        unsigned __int8 *a2,
        unsigned int a3,
        __int16 a4,
        struct _ASF_DATA_DESCRIPTOR *a5)
{
  __int16 v10; // [rsp+20h] [rbp-38h]
  char v11; // [rsp+60h] [rbp+8h] BYREF

  CAutoCritSec::CAutoCritSec((CAutoCritSec *)&v11, this[1625]);
  if ( !*((_DWORD *)this + 4) || *((_DWORD *)this + 3) )
  {
    CAutoCritSec::~CAutoCritSec((CAutoCritSec *)&v11);
    return 1;
  }
  else
  {
    if ( *((_DWORD *)this + 17) == 2 )
    {
      v10 = a4;
      (*((void (__fastcall **)(char *, unsigned __int8 *, _QWORD, GUID *, __int16, struct _ASF_DATA_DESCRIPTOR *))*(this - 1)
       + 13))(
        (char *)this - 8,
        a2,
        a3,
        &CLSID_ASFDataUnitData,
        v10,
        a5);
    }
    CAutoCritSec::~CAutoCritSec((CAutoCritSec *)&v11);
    return 0;
  }
}

```

## disassembly

```asm
0x18003dc50  mov     [rsp+arg_8], rbx
0x18003dc55  mov     [rsp+arg_10], rbp
0x18003dc5a  push    rsi
0x18003dc5b  push    rdi
0x18003dc5c  push    r14
0x18003dc5e  sub     rsp, 40h
0x18003dc62  mov     r14, rdx
0x18003dc65  mov     rbx, rcx
0x18003dc68  mov     rdx, [rcx+32C8h]; struct IWMSCriticalSection *
0x18003dc6f  movzx   esi, r9w
0x18003dc73  lea     rcx, [rsp+58h+arg_0]; this
0x18003dc78  mov     ebp, r8d
0x18003dc7b  call    ??0CAutoCritSec@@QEAA@PEAUIWMSCriticalSection@@@Z; CAutoCritSec::CAutoCritSec(IWMSCriticalSection *)
0x18003dc80  cmp     dword ptr [rbx+10h], 0
0x18003dc84  jz      short loc_18003DCD0
0x18003dc86  cmp     dword ptr [rbx+0Ch], 0
0x18003dc8a  jnz     short loc_18003DCD0
0x18003dc8c  cmp     dword ptr [rbx+44h], 2
0x18003dc90  jnz     short loc_18003DCC2
0x18003dc92  mov     rax, [rbx-8]
0x18003dc96  lea     r9, CLSID_ASFDataUnitData
0x18003dc9d  mov     rdx, [rsp+58h+arg_20]
0x18003dca5  lea     rcx, [rbx-8]
0x18003dca9  mov     [rsp+58h+var_30], rdx
0x18003dcae  mov     r8d, ebp
0x18003dcb1  mov     rdx, r14
0x18003dcb4  mov     [rsp+58h+var_38], si
0x18003dcb9  mov     rax, [rax+68h]
0x18003dcbd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003dcc2  lea     rcx, [rsp+58h+arg_0]; this
0x18003dcc7  call    ??1CAutoCritSec@@QEAA@XZ; CAutoCritSec::~CAutoCritSec(void)
0x18003dccc  xor     eax, eax
0x18003dcce  jmp     short loc_18003DCDF
0x18003dcd0  lea     rcx, [rsp+58h+arg_0]; this
0x18003dcd5  call    ??1CAutoCritSec@@QEAA@XZ; CAutoCritSec::~CAutoCritSec(void)
0x18003dcda  mov     eax, 1
0x18003dcdf  mov     rbx, [rsp+58h+arg_8]
0x18003dce4  mov     rbp, [rsp+58h+arg_10]
0x18003dce9  add     rsp, 40h
0x18003dced  pop     r14
0x18003dcef  pop     rdi
0x18003dcf0  pop     rsi
0x18003dcf1  retn
```
