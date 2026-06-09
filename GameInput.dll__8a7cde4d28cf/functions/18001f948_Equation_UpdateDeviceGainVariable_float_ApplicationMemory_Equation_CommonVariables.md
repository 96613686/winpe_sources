# Equation::UpdateDeviceGainVariable(float,ApplicationMemory &,Equation::CommonVariables *)

- ea: `0x18001f948`
- end: `0x18001fa34`
- name: `?UpdateDeviceGainVariable@Equation@@IEAAJMAEAVApplicationMemory@@PEAUCommonVariables@1@@Z`
- size: `236`
- prototype: `__int64 __fastcall(Equation *__hidden this, float, struct ApplicationMemory *, struct Equation::CommonVariables *)`
- caller_count: `4`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18001f610`
- `0x18001f6e0`
- `0x18001f7b0`
- `0x18001f880`

## callees

- `0x180001304`
- `0x180017e70`
- `0x18001f948`
- `0x180020718`

## pseudocode

```c
// local variable allocation has failed, the output may be wrong!
__int64 __fastcall Equation::UpdateDeviceGainVariable(
        Equation *this,
        double a2,
        struct ApplicationMemory *a3,
        struct Equation::CommonVariables *a4)
{
  unsigned __int16 v5; // ax
  void *v6; // r8
  ApplicationMemory *v7; // r10
  int updated; // ebx
  __int64 v10; // r8
  __int64 v11; // r9
  const char *v12; // [rsp+40h] [rbp-28h] BYREF
  int v13; // [rsp+78h] [rbp+10h] BYREF
  int v14; // [rsp+88h] [rbp+20h] BYREF

  if ( *((float *)a4 + 1) == *(float *)&a2 )
    return 0;
  v5 = Equation::LookupVariableAddress(this, L"DEVICEGAIN");
  if ( v5 == 0xFFFF )
    return 2147549183LL;
  updated = ApplicationMemory::UpdateVariable(v7, v5, v6, _mm_cvtsi128_si32(*(__m128i *)&a2));
  if ( updated >= 0 )
  {
    *((_DWORD *)a4 + 1) = LODWORD(a2);
    return 0;
  }
  if ( (unsigned int)dword_180069000 > 2 && (qword_180069010 & 8) != 0 && (qword_180069018 & 8) == qword_180069018 )
  {
    v13 = updated;
    v12 = "onecore\\xbox\\gameinput\\feedback\\gipequationmanager\\Equation.cpp";
    v14 = 400;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      qword_180069010,
      (unsigned __int8 *)&word_18005E5AE,
      v10,
      v11,
      (__int64 **)&v12,
      (__int64)&v14,
      (__int64)&v13);
  }
  return (unsigned int)updated;
}

```

## disassembly

```asm
0x18001f948  mov     [rsp+arg_0], rbx
0x18001f94d  push    rdi
0x18001f94e  sub     rsp, 60h
0x18001f952  movss   xmm0, dword ptr [r9+4]
0x18001f958  mov     rdi, r9
0x18001f95b  movaps  [rsp+68h+var_18], xmm6
0x18001f960  mov     r10, r8
0x18001f963  movaps  xmm6, xmm1
0x18001f966  ucomiss xmm0, xmm6
0x18001f969  jp      short loc_18001F971
0x18001f96b  jz      loc_18001FA21
0x18001f971  lea     rdx, aDevicegain; "DEVICEGAIN"
0x18001f978  call    ?LookupVariableAddress@Equation@@IEAAGPEBG@Z; Equation::LookupVariableAddress(ushort const *)
0x18001f97d  mov     ecx, 0FFFFh
0x18001f982  cmp     ax, cx
0x18001f985  jnz     short loc_18001F991
0x18001f987  mov     eax, 8000FFFFh
0x18001f98c  jmp     loc_18001FA23
0x18001f991  movd    r9d, xmm6; unsigned int
0x18001f996  movzx   edx, ax; unsigned __int16
0x18001f999  mov     rcx, r10; this
0x18001f99c  call    ?UpdateVariable@ApplicationMemory@@QEAAJGPEAXI@Z; ApplicationMemory::UpdateVariable(ushort,void *,uint)
0x18001f9a1  mov     ebx, eax
0x18001f9a3  test    eax, eax
0x18001f9a5  jns     short loc_18001FA1C
0x18001f9a7  mov     ecx, cs:dword_180069000
0x18001f9ad  cmp     ecx, 2
0x18001f9b0  jbe     short loc_18001FA18
0x18001f9b2  mov     rdx, cs:qword_180069018
0x18001f9b9  mov     rcx, cs:qword_180069010
0x18001f9c0  test    cl, 8
0x18001f9c3  jz      short loc_18001FA18
0x18001f9c5  mov     rax, rdx
0x18001f9c8  and     eax, 8
0x18001f9cb  cmp     rax, rdx
0x18001f9ce  jnz     short loc_18001FA18
0x18001f9d0  lea     rax, aOnecoreXboxGam_14; "onecore\\xbox\\gameinput\\feedback\\gip"...
0x18001f9d7  mov     [rsp+68h+arg_8], ebx
0x18001f9db  mov     [rsp+68h+var_28], rax
0x18001f9e0  lea     rdx, word_18005E5AE
0x18001f9e7  lea     rax, [rsp+68h+arg_8]
0x18001f9ec  mov     [rsp+68h+arg_18], 190h
0x18001f9f7  mov     [rsp+68h+var_38], rax
0x18001f9fc  lea     rax, [rsp+68h+arg_18]
0x18001fa04  mov     [rsp+68h+var_40], rax
0x18001fa09  lea     rax, [rsp+68h+var_28]
0x18001fa0e  mov     [rsp+68h+var_48], rax
0x18001fa13  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_GameInputEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18001fa18  mov     eax, ebx
0x18001fa1a  jmp     short loc_18001FA23
0x18001fa1c  movss   dword ptr [rdi+4], xmm6
0x18001fa21  xor     eax, eax
0x18001fa23  mov     rbx, [rsp+68h+arg_0]
0x18001fa28  movaps  xmm6, [rsp+68h+var_18]
0x18001fa2d  add     rsp, 60h
0x18001fa31  pop     rdi
0x18001fa32  retn
```
