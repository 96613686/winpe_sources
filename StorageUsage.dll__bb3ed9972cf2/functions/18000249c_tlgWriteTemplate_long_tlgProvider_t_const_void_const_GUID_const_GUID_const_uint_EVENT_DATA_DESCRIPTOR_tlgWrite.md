# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>,_tlgWrapBuffer<_UNICODE_STRING>,_tlgWrapperArray<8>,_tlgWrapperArray<1>,_tlgWrapperByVal<2>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<2> const &,_tlgWrapperByVal<4> const &,_tlgWrapBuffer<_UNICODE_STRING> const &,_tlgWrapperArray<8> const &,_tlgWrapperArray<1> const &,_tlgWrapperByVal<2> const &)

- ea: `0x18000249c`
- end: `0x1800025aa`
- name: `??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$01@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapBuffer@U_UNICODE_STRING@@@@U?$_tlgWrapperArray@$07@@U?$_tlgWrapperArray@$00@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$01@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapBuffer@U_UNICODE_STRING@@@@AEBU?$_tlgWrapperArray@$07@@AEBU?$_tlgWrapperArray@$00@@4@Z`
- size: `270`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, __int64, __int64, __int64, unsigned __int16 **, __int64 *, __int64 *, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18001e428`

## callees

- `0x180001010`
- `0x1800050f0`

## pseudocode

```c
__int64 __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>,_tlgWrapBuffer<_UNICODE_STRING>,_tlgWrapperArray<8>,_tlgWrapperArray<1>,_tlgWrapperByVal<2>>(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        __int64 a7,
        unsigned __int16 **a8,
        __int64 *a9,
        __int64 *a10,
        __int64 a11)
{
  int v11; // ecx
  _BYTE v13[32]; // [rsp+30h] [rbp-B1h] BYREF
  __int64 v14; // [rsp+50h] [rbp-91h]
  __int64 v15; // [rsp+58h] [rbp-89h]
  __int64 v16; // [rsp+60h] [rbp-81h]
  __int64 v17; // [rsp+68h] [rbp-79h]
  __int64 v18; // [rsp+70h] [rbp-71h]
  __int64 v19; // [rsp+78h] [rbp-69h]
  _DWORD *v20; // [rsp+80h] [rbp-61h]
  __int64 v21; // [rsp+88h] [rbp-59h]
  __int64 v22; // [rsp+90h] [rbp-51h]
  _DWORD v23[2]; // [rsp+98h] [rbp-49h] BYREF
  __int64 *v24; // [rsp+A0h] [rbp-41h]
  __int64 v25; // [rsp+A8h] [rbp-39h]
  __int64 v26; // [rsp+B0h] [rbp-31h]
  int v27; // [rsp+B8h] [rbp-29h]
  int v28; // [rsp+BCh] [rbp-25h]
  __int64 *v29; // [rsp+C0h] [rbp-21h]
  __int64 v30; // [rsp+C8h] [rbp-19h]
  __int64 v31; // [rsp+D0h] [rbp-11h]
  int v32; // [rsp+D8h] [rbp-9h]
  int v33; // [rsp+DCh] [rbp-5h]
  __int64 v34; // [rsp+E0h] [rbp-1h]
  __int64 v35; // [rsp+E8h] [rbp+7h]

  v34 = a11;
  v35 = 2;
  v30 = 2;
  v33 = 0;
  v25 = 2;
  v31 = *a10;
  v32 = *((unsigned __int16 *)a10 + 4);
  v29 = a10 + 1;
  v28 = 0;
  v21 = 2;
  v26 = *a9;
  v27 = 8 * *((unsigned __int16 *)a9 + 4);
  v20 = v23;
  v24 = a9 + 1;
  v11 = **a8;
  v22 = *((_QWORD *)*a8 + 1);
  v18 = a7;
  v16 = a6;
  v14 = a5;
  v23[0] = v11;
  v23[1] = 0;
  v19 = 4;
  v17 = 2;
  v15 = 8;
  return tlgWriteTransfer_EventWriteTransfer(&dword_180040010, a2, 0, 0, 12, v13);
}

```

## disassembly

```asm
0x18000249c  push    rbp
0x18000249e  lea     rbp, [rsp-1Fh]
0x1800024a3  sub     rsp, 100h
0x1800024aa  mov     rax, cs:__security_cookie
0x1800024b1  xor     rax, rsp
0x1800024b4  mov     [rbp+1Fh+var_10], rax
0x1800024b8  mov     rax, [rbp+1Fh+arg_50]
0x1800024bc  xor     r9d, r9d
0x1800024bf  mov     [rbp+1Fh+var_20], rax
0x1800024c3  xor     r8d, r8d
0x1800024c6  mov     rax, [rbp+1Fh+arg_48]
0x1800024ca  mov     [rbp+1Fh+var_18], 2
0x1800024d2  mov     [rbp+1Fh+var_38], 2
0x1800024da  mov     [rbp+1Fh+var_24], r9d
0x1800024de  lea     rcx, [rax+8]
0x1800024e2  mov     [rbp+1Fh+var_58], 2
0x1800024ea  mov     rax, [rax]
0x1800024ed  mov     [rbp+1Fh+var_30], rax
0x1800024f1  movzx   eax, word ptr [rcx]
0x1800024f4  mov     [rbp+1Fh+var_28], eax
0x1800024f7  mov     rax, [rbp+1Fh+arg_40]
0x1800024fb  mov     [rbp+1Fh+var_40], rcx
0x1800024ff  mov     [rbp+1Fh+var_44], r9d
0x180002503  mov     [rbp+1Fh+var_78], 2
0x18000250b  lea     rcx, [rax+8]
0x18000250f  mov     rax, [rax]
0x180002512  mov     [rbp+1Fh+var_50], rax
0x180002516  movzx   eax, word ptr [rcx]
0x180002519  shl     eax, 3
0x18000251c  mov     [rbp+1Fh+var_48], eax
0x18000251f  lea     rax, [rbp+1Fh+var_68]
0x180002523  mov     [rbp+1Fh+var_80], rax
0x180002527  mov     rax, [rbp+1Fh+arg_38]
0x18000252b  mov     [rbp+1Fh+var_60], rcx
0x18000252f  mov     rax, [rax]
0x180002532  movzx   ecx, word ptr [rax]
0x180002535  mov     rax, [rax+8]
0x180002539  mov     [rbp+1Fh+var_70], rax
0x18000253d  mov     rax, [rbp+1Fh+arg_30]
0x180002541  mov     [rbp+1Fh+var_90], rax
0x180002545  mov     rax, [rbp+1Fh+arg_28]
0x180002549  mov     [rsp+100h+var_A0], rax
0x18000254e  mov     rax, [rbp+1Fh+arg_20]
0x180002552  mov     [rsp+100h+var_B0], rax
0x180002557  lea     rax, [rsp+100h+var_D0]
0x18000255c  mov     [rbp+1Fh+var_68], ecx
0x18000255f  lea     rcx, dword_180040010
0x180002566  mov     [rsp+100h+var_D8], rax
0x18000256b  mov     [rsp+100h+var_E0], 0Ch
0x180002573  mov     [rbp+1Fh+var_64], r9d
0x180002577  mov     [rbp+1Fh+var_88], 4
0x18000257f  mov     [rbp+1Fh+var_98], 2
0x180002587  mov     [rsp+100h+var_A8], 8
0x180002590  call    _tlgWriteTransfer_EventWriteTransfer
0x180002595  mov     rcx, [rbp+1Fh+var_10]
0x180002599  xor     rcx, rsp; StackCookie
0x18000259c  call    __security_check_cookie
0x1800025a1  add     rsp, 100h
0x1800025a8  pop     rbp
0x1800025a9  retn
```
