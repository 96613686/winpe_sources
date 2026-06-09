# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapSid<_SID>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapSid<_SID> const &,_tlgWrapperByVal<4> const &)

- ea: `0x14000116c`
- end: `0x14000123c`
- name: `??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapSid@U_SID@@@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapSid@U_SID@@@@AEBU?$_tlgWrapperByVal@$03@@@Z`
- size: `208`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x1400016a0`
- `0x140002138`

## callees

- `0x14000116c`
- `0x1400012f0`
- `0x14000a680`

## pseudocode

```c
NTSTATUS __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapSid<_SID>,_tlgWrapperByVal<4>>(
        __int64 a1,
        unsigned __int8 *a2,
        __int64 a3,
        __int64 a4,
        __int64 **a5,
        __int64 *a6,
        __int64 a7)
{
  int v7; // eax
  __int64 *v8; // rcx
  __int64 v9; // rax
  int v10; // eax
  struct _EVENT_DATA_DESCRIPTOR v12; // [rsp+30h] [rbp-68h] BYREF
  __int64 *v13; // [rsp+50h] [rbp-48h]
  int v14; // [rsp+58h] [rbp-40h]
  int v15; // [rsp+5Ch] [rbp-3Ch]
  __int64 v16; // [rsp+60h] [rbp-38h]
  int v17; // [rsp+68h] [rbp-30h]
  int v18; // [rsp+6Ch] [rbp-2Ch]
  __int64 v19; // [rsp+70h] [rbp-28h]
  __int64 v20; // [rsp+78h] [rbp-20h]

  v19 = a7;
  v20 = 4;
  v7 = *(unsigned __int8 *)(*a6 + 1);
  v16 = *a6;
  v17 = 4 * v7 + 8;
  v18 = 0;
  v8 = *a5;
  if ( *a5 )
  {
    v9 = -1;
    do
      ++v9;
    while ( *((_WORD *)v8 + v9) );
    v10 = 2 * v9 + 2;
  }
  else
  {
    v8 = &qword_14000C868;
    v10 = 2;
  }
  v14 = v10;
  v13 = v8;
  v15 = 0;
  return tlgWriteTransfer_EtwWriteTransfer((__int64)&dword_140012050, a2, 0, 0, 5u, &v12);
}

```

## disassembly

```asm
0x14000116c  mov     r11, rsp
0x14000116f  sub     rsp, 98h
0x140001176  mov     rax, cs:__security_cookie
0x14000117d  xor     rax, rsp
0x140001180  mov     [rsp+98h+var_18], rax
0x140001188  mov     rax, [rsp+98h+arg_30]
0x140001190  xor     r8d, r8d; int
0x140001193  mov     [r11-28h], rax
0x140001197  mov     rax, [rsp+98h+arg_28]
0x14000119f  mov     qword ptr [r11-20h], 4
0x1400011a7  mov     rcx, [rax]
0x1400011aa  movzx   eax, byte ptr [rcx+1]
0x1400011ae  mov     [r11-38h], rcx
0x1400011b2  lea     eax, ds:8[rax*4]
0x1400011b9  mov     [rsp+98h+var_30], eax
0x1400011bd  mov     rax, [rsp+98h+arg_20]
0x1400011c5  mov     [r11-2Ch], r8d
0x1400011c9  mov     rcx, [rax]
0x1400011cc  test    rcx, rcx
0x1400011cf  jz      short loc_1400011E8
0x1400011d1  or      rax, 0FFFFFFFFFFFFFFFFh
0x1400011d5  inc     rax
0x1400011d8  cmp     [rcx+rax*2], r8w
0x1400011dd  jnz     short loc_1400011D5
0x1400011df  lea     eax, ds:2[rax*2]
0x1400011e6  jmp     short loc_1400011F4
0x1400011e8  lea     rcx, qword_14000C868
0x1400011ef  mov     eax, 2
0x1400011f4  mov     [rsp+98h+var_40], eax
0x1400011f8  xor     r9d, r9d; int
0x1400011fb  lea     rax, [rsp+98h+var_68]
0x140001200  mov     [rsp+98h+var_48], rcx
0x140001205  mov     [rsp+98h+var_70], rax; PEVENT_DATA_DESCRIPTOR
0x14000120a  lea     rcx, dword_140012050; int
0x140001211  mov     [rsp+98h+var_78], 5; ULONG
0x140001219  mov     [rsp+98h+var_3C], r8d
0x14000121e  call    _tlgWriteTransfer_EtwWriteTransfer
0x140001223  mov     rcx, [rsp+98h+var_18]
0x14000122b  xor     rcx, rsp; StackCookie
0x14000122e  call    __security_check_cookie
0x140001233  add     rsp, 98h
0x14000123a  retn
```
