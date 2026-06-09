# _CSebiCreateCustomEvent

- ea: `0x18001fea0`
- end: `0x1800200ae`
- name: `_CSebiCreateCustomEvent`
- size: `526`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `file_ops, broker_com_uri`

## callees

- `0x1800030e0`
- `0x180005a50`
- `0x1800076a0`
- `0x180009740`
- `0x180012a80`
- `0x18001cf74`
- `0x18001d364`
- `0x18001d39c`
- `0x18001fea0`
- `0x180022440`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CSebiCreateCustomEvent(
        __int64 a1,
        __int64 a2,
        unsigned int a3,
        const void *a4,
        int a5,
        _QWORD *a6,
        _QWORD *a7)
{
  unsigned __int64 v8; // rbx
  __int64 v10; // rcx
  unsigned int Event; // ebx
  _QWORD *v12; // rcx
  __int64 v13; // rdx
  _DWORD *v14; // rdi
  void *v15; // rax
  _DWORD *v17; // [rsp+30h] [rbp-98h]
  __int64 v18; // [rsp+38h] [rbp-90h] BYREF
  std::_Ref_count_base *v19; // [rsp+40h] [rbp-88h]
  _OWORD v20[3]; // [rsp+50h] [rbp-78h] BYREF
  __int64 v21; // [rsp+80h] [rbp-48h]

  v8 = a3;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 33, &WPP_bd1538f8470038ec001d4a44b16548c6_Traceguids);
  *a6 = 0;
  *a7 = 0;
  CBroker::SebBroker::GetInstance(&v18);
  if ( !v18 )
  {
    Event = 21;
LABEL_26:
    v12 = WPP_GLOBAL_Control;
    goto LABEL_27;
  }
  if ( *(_DWORD *)(a2 + 8) != 4148 )
  {
    Event = 87;
    goto LABEL_26;
  }
  if ( *(_QWORD *)a2 )
  {
    v14 = 0;
    if ( a4 )
    {
      if ( (_DWORD)v8 )
        goto LABEL_16;
    }
    else if ( !(_DWORD)v8 )
    {
LABEL_16:
      if ( a4 )
      {
        try
        {
          v14 = operator new(0x10u);
          v17 = v14;
          v14[3] = a5;
          v14[2] = v8;
          v15 = operator new[](v8);
          *(_QWORD *)v14 = v15;
          memcpy_0(v15, a4, v8);
        }
        catch ( ... )
        {
          Event = 14;
          v14 = v17;
          goto LABEL_22;
        }
      }
      v20[0] = *(_OWORD *)a2;
      v20[1] = *(_OWORD *)(a2 + 16);
      v20[2] = *(_OWORD *)(a2 + 32);
      v21 = *(_QWORD *)(a2 + 48);
      Event = _SebiCreateEvent(
                v10,
                (const struct _CSebiSystemEventCreationParameter *)v20,
                (const struct CBroker::_CustomData *)v14,
                a6,
                a7);
LABEL_22:
      if ( v14 )
      {
        if ( *(_QWORD *)v14 )
          operator delete(*(void **)v14);
        operator delete(v14);
      }
      goto LABEL_26;
    }
    v12 = WPP_GLOBAL_Control;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u )
      goto LABEL_13;
    v13 = 35;
    goto LABEL_12;
  }
  v12 = WPP_GLOBAL_Control;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u )
    goto LABEL_13;
  v13 = 34;
LABEL_12:
  WPP_SF_(v12[2], v13, &WPP_bd1538f8470038ec001d4a44b16548c6_Traceguids);
  v12 = WPP_GLOBAL_Control;
LABEL_13:
  Event = 87;
LABEL_27:
  if ( (*((_BYTE *)v12 + 28) & 8) != 0 && *((_BYTE *)v12 + 25) >= 4u )
    WPP_SF_d(v12[2], 36, &WPP_bd1538f8470038ec001d4a44b16548c6_Traceguids, Event);
  if ( v19 )
    std::_Ref_count_base::_Decref(v19);
  return Event;
}

```

## disassembly

```asm
0x18001fea0  push    rbx
0x18001fea2  push    rsi
0x18001fea3  push    rdi
0x18001fea4  push    r12
0x18001fea6  push    r14
0x18001fea8  push    r15
0x18001feaa  sub     rsp, 98h
0x18001feb1  mov     r14, r9
0x18001feb4  mov     ebx, r8d
0x18001feb7  mov     rsi, rdx
0x18001feba  mov     rcx, cs:WPP_GLOBAL_Control
0x18001fec1  test    byte ptr [rcx+1Ch], 8
0x18001fec5  jz      short loc_18001FEE2
0x18001fec7  cmp     byte ptr [rcx+19h], 4
0x18001fecb  jb      short loc_18001FEE2
0x18001fecd  mov     edx, 21h ; '!'
0x18001fed2  lea     r8, WPP_bd1538f8470038ec001d4a44b16548c6_Traceguids
0x18001fed9  mov     rcx, [rcx+10h]
0x18001fedd  call    WPP_SF_
0x18001fee2  xor     eax, eax
0x18001fee4  mov     r15, [rsp+0C8h+arg_28]
0x18001feec  mov     [r15], rax
0x18001feef  mov     r12, [rsp+0C8h+arg_30]
0x18001fef7  mov     [r12], rax
0x18001fefb  lea     rcx, [rsp+0C8h+var_90]
0x18001ff00  call    ?GetInstance@SebBroker@CBroker@@SA?AV?$shared_ptr@VSebBroker@CBroker@@@std@@XZ; CBroker::SebBroker::GetInstance(void)
0x18001ff05  nop
0x18001ff06  cmp     [rsp+0C8h+var_90], 0
0x18001ff0c  jnz     short loc_18001FF18
0x18001ff0e  mov     ebx, 15h
0x18001ff13  jmp     loc_180020060
0x18001ff18  cmp     dword ptr [rsi+8], 1034h
0x18001ff1f  jz      short loc_18001FF2B
0x18001ff21  mov     ebx, 57h ; 'W'
0x18001ff26  jmp     loc_180020060
0x18001ff2b  mov     rax, [rsi]
0x18001ff2e  test    eax, eax
0x18001ff30  jnz     short loc_18001FF71
0x18001ff32  shr     rax, 20h
0x18001ff36  test    eax, eax
0x18001ff38  jnz     short loc_18001FF71
0x18001ff3a  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ff41  test    byte ptr [rcx+1Ch], 8
0x18001ff45  jz      short loc_18001FF67
0x18001ff47  cmp     byte ptr [rcx+19h], 4
0x18001ff4b  jb      short loc_18001FF67
0x18001ff4d  lea     edx, [rax+22h]
0x18001ff50  lea     r8, WPP_bd1538f8470038ec001d4a44b16548c6_Traceguids
0x18001ff57  mov     rcx, [rcx+10h]
0x18001ff5b  call    WPP_SF_
0x18001ff60  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ff67  mov     ebx, 57h ; 'W'
0x18001ff6c  jmp     loc_180020067
0x18001ff71  xor     edi, edi
0x18001ff73  mov     [rsp+0C8h+var_98], rdi
0x18001ff78  test    r14, r14
0x18001ff7b  jnz     loc_180020008
0x18001ff81  test    ebx, ebx
0x18001ff83  jnz     loc_180020010
0x18001ff89  test    r14, r14
0x18001ff8c  jz      short loc_18001FFC7
0x18001ff8e  mov     ecx, 10h; Size
0x18001ff93  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001ff98  mov     rdi, rax
0x18001ff9b  mov     [rsp+0C8h+var_98], rax
0x18001ffa0  mov     eax, [rsp+0C8h+arg_20]
0x18001ffa7  mov     [rdi+0Ch], eax
0x18001ffaa  mov     [rdi+8], ebx
0x18001ffad  mov     rcx, rbx; unsigned __int64
0x18001ffb0  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18001ffb5  mov     [rdi], rax
0x18001ffb8  mov     r8, rbx; Size
0x18001ffbb  mov     rdx, r14; Src
0x18001ffbe  mov     rcx, rax; void *
0x18001ffc1  call    memcpy_0
0x18001ffc6  nop
0x18001ffc7  movups  xmm0, xmmword ptr [rsi]
0x18001ffca  movaps  [rsp+0C8h+var_78], xmm0
0x18001ffcf  movups  xmm1, xmmword ptr [rsi+10h]
0x18001ffd3  movaps  [rsp+0C8h+var_68], xmm1
0x18001ffd8  movups  xmm0, xmmword ptr [rsi+20h]
0x18001ffdc  movaps  [rsp+0C8h+var_58], xmm0
0x18001ffe1  movsd   xmm1, qword ptr [rsi+30h]
0x18001ffe6  movsd   [rsp+0C8h+var_48], xmm1
0x18001ffef  mov     [rsp+0C8h+var_A8], r12
0x18001fff4  mov     r9, r15
0x18001fff7  mov     r8, rdi
0x18001fffa  lea     rdx, [rsp+0C8h+var_78]
0x18001ffff  call    ?_SebiCreateEvent@@YAKPEAXU_CSebiSystemEventCreationParameter@@PEAU_CustomData@CBroker@@PEAU_CBROKERED_EVENT_ID@@PEAPEAX@Z; _SebiCreateEvent(void *,_CSebiSystemEventCreationParameter,CBroker::_CustomData *,_CBROKERED_EVENT_ID *,void * *)
0x180020004  mov     ebx, eax
0x180020006  jmp     short loc_180020041
0x180020008  test    ebx, ebx
0x18002000a  jnz     loc_18001FF89
0x180020010  mov     rcx, cs:WPP_GLOBAL_Control
0x180020017  test    byte ptr [rcx+1Ch], 8
0x18002001b  jz      loc_18001FF67
0x180020021  cmp     byte ptr [rcx+19h], 4
0x180020025  jb      loc_18001FF67
0x18002002b  mov     edx, 23h ; '#'; unsigned __int64
0x180020030  jmp     loc_18001FF50
0x180020035  mov     ebx, dword ptr [rsp+0C8h+arg_30]
0x18002003c  mov     rdi, [rsp+0C8h+var_98]
0x180020041  test    rdi, rdi
0x180020044  jz      short loc_180020060
0x180020046  mov     rcx, [rdi]; void *
0x180020049  test    rcx, rcx
0x18002004c  jz      short loc_180020053
0x18002004e  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180020053  mov     edx, 10h; unsigned __int64
0x180020058  mov     rcx, rdi; void *
0x18002005b  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180020060  mov     rcx, cs:WPP_GLOBAL_Control
0x180020067  test    byte ptr [rcx+1Ch], 8
0x18002006b  jz      short loc_18002008C
0x18002006d  cmp     byte ptr [rcx+19h], 4
0x180020071  jb      short loc_18002008C
0x180020073  mov     edx, 24h ; '$'
0x180020078  mov     r9d, ebx
0x18002007b  lea     r8, WPP_bd1538f8470038ec001d4a44b16548c6_Traceguids
0x180020082  mov     rcx, [rcx+10h]
0x180020086  call    WPP_SF_d
0x18002008b  nop
0x18002008c  mov     rcx, [rsp+0C8h+var_88]; this
0x180020091  test    rcx, rcx
0x180020094  jz      short loc_18002009B
0x180020096  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18002009b  mov     eax, ebx
0x18002009d  add     rsp, 98h
0x1800200a4  pop     r15
0x1800200a6  pop     r14
0x1800200a8  pop     r12
0x1800200aa  pop     rdi
0x1800200ab  pop     rsi
0x1800200ac  pop     rbx
0x1800200ad  retn
```
