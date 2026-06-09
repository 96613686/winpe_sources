# CRdpSessionAgentProxy::Advise(ushort *,IRdpSessionAgent *)

- ea: `0x1400039e0`
- end: `0x140003c0d`
- name: `?Advise@CRdpSessionAgentProxy@@UEAAJPEAGPEAUIRdpSessionAgent@@@Z`
- size: `557`
- prototype: `__int64 __fastcall(CRdpSessionAgentProxy *this, unsigned __int16 *, struct IRdpSessionAgent *)`
- caller_count: `0`
- callee_count: `5`
- tags: `service_task`

## callees

- `0x140002738`
- `0x1400027cc`
- `0x1400039e0`
- `0x1400056c9`
- `0x140006010`

## import_xrefs

- `OLEAUT32!__imp_SysStringByteLen` at `0x140003aaf`
- `OLEAUT32!__imp_SysStringByteLen` at `0x140003aaf`

## pseudocode

```c
__int64 __fastcall CRdpSessionAgentProxy::Advise(
        CRdpSessionAgentProxy *this,
        unsigned __int16 *a2,
        struct IRdpSessionAgent *a3)
{
  unsigned int CurrentThreadActivityIdPrefix; // eax
  unsigned int v7; // ebx
  unsigned int v8; // eax
  __int64 v9; // rdx
  unsigned int v10; // eax
  __int64 v11; // rdx
  unsigned int v12; // eax

  if ( !*((_QWORD *)this + 11) )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_Dd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        30,
        WPP_a4a5f05f0f7b31c3267dbefd3b846115_Traceguids,
        CurrentThreadActivityIdPrefix,
        -2147483638);
    }
    return (unsigned int)-2147483638;
  }
  if ( !a2 )
  {
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return (unsigned int)-2147467261;
    }
    v8 = RdpWppGetCurrentThreadActivityIdPrefix();
    v9 = 31;
LABEL_12:
    WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), v9, WPP_a4a5f05f0f7b31c3267dbefd3b846115_Traceguids, v8, -2147467261);
    return (unsigned int)-2147467261;
  }
  if ( SysStringByteLen(a2) != 64 )
  {
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return (unsigned int)-2147024891;
    }
    v10 = RdpWppGetCurrentThreadActivityIdPrefix();
    v11 = 32;
LABEL_19:
    WPP_SF_Dd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v11,
      WPP_a4a5f05f0f7b31c3267dbefd3b846115_Traceguids,
      v10,
      -2147024891);
    return (unsigned int)-2147024891;
  }
  if ( memcmp_0(a2, *((const void **)this + 11), 0x40u) )
  {
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return (unsigned int)-2147024891;
    }
    v10 = RdpWppGetCurrentThreadActivityIdPrefix();
    v11 = 33;
    goto LABEL_19;
  }
  if ( !a3 )
  {
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return (unsigned int)-2147467261;
    }
    v8 = RdpWppGetCurrentThreadActivityIdPrefix();
    v9 = 34;
    goto LABEL_12;
  }
  if ( *((_QWORD *)this + 7) )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v12 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_Dd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        35,
        WPP_a4a5f05f0f7b31c3267dbefd3b846115_Traceguids,
        v12,
        -2147418113);
    }
    return (unsigned int)-2147418113;
  }
  else
  {
    *((_QWORD *)this + 7) = a3;
    v7 = 0;
    (*(void (__fastcall **)(struct IRdpSessionAgent *))(*(_QWORD *)a3 + 8LL))(a3);
  }
  return v7;
}

```

## disassembly

```asm
0x1400039e0  mov     [rsp+arg_0], rbx
0x1400039e5  mov     [rsp+arg_8], rsi
0x1400039ea  push    rdi
0x1400039eb  sub     rsp, 30h
0x1400039ef  cmp     qword ptr [rcx+58h], 0
0x1400039f4  mov     rdi, r8
0x1400039f7  mov     rbx, rdx
0x1400039fa  mov     rsi, rcx
0x1400039fd  jnz     short loc_140003A54
0x1400039ff  mov     rcx, cs:WPP_GLOBAL_Control
0x140003a06  lea     rax, WPP_GLOBAL_Control
0x140003a0d  cmp     rcx, rax
0x140003a10  jz      short loc_140003A4A
0x140003a12  test    byte ptr [rcx+1Ch], 8
0x140003a16  jz      short loc_140003A4A
0x140003a18  cmp     byte ptr [rcx+19h], 2
0x140003a1c  jb      short loc_140003A4A
0x140003a1e  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140003a23  mov     rcx, cs:WPP_GLOBAL_Control
0x140003a2a  lea     r8, WPP_a4a5f05f0f7b31c3267dbefd3b846115_Traceguids
0x140003a31  mov     edx, 1Eh
0x140003a36  mov     [rsp+38h+var_18], 8000000Ah
0x140003a3e  mov     r9d, eax
0x140003a41  mov     rcx, [rcx+10h]
0x140003a45  call    WPP_SF_Dd
0x140003a4a  mov     ebx, 8000000Ah
0x140003a4f  jmp     loc_140003BFB
0x140003a54  test    rbx, rbx
0x140003a57  jnz     short loc_140003AAC
0x140003a59  mov     rcx, cs:WPP_GLOBAL_Control
0x140003a60  lea     rax, WPP_GLOBAL_Control
0x140003a67  cmp     rcx, rax
0x140003a6a  jz      short loc_140003AA2
0x140003a6c  test    byte ptr [rcx+1Ch], 8
0x140003a70  jz      short loc_140003AA2
0x140003a72  cmp     byte ptr [rcx+19h], 2
0x140003a76  jb      short loc_140003AA2
0x140003a78  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140003a7d  lea     edx, [rbx+1Fh]
0x140003a80  mov     rcx, cs:WPP_GLOBAL_Control
0x140003a87  lea     r8, WPP_a4a5f05f0f7b31c3267dbefd3b846115_Traceguids
0x140003a8e  mov     r9d, eax
0x140003a91  mov     [rsp+38h+var_18], 80004003h
0x140003a99  mov     rcx, [rcx+10h]
0x140003a9d  call    WPP_SF_Dd
0x140003aa2  mov     ebx, 80004003h
0x140003aa7  jmp     loc_140003BFB
0x140003aac  mov     rcx, rbx; bstr
0x140003aaf  call    cs:__imp_SysStringByteLen
0x140003ab5  mov     r8d, 40h ; '@'; Size
0x140003abb  cmp     eax, r8d
0x140003abe  jz      short loc_140003B15
0x140003ac0  mov     rcx, cs:WPP_GLOBAL_Control
0x140003ac7  lea     rax, WPP_GLOBAL_Control
0x140003ace  cmp     rcx, rax
0x140003ad1  jz      short loc_140003B0B
0x140003ad3  test    byte ptr [rcx+1Ch], 8
0x140003ad7  jz      short loc_140003B0B
0x140003ad9  cmp     byte ptr [rcx+19h], 2
0x140003add  jb      short loc_140003B0B
0x140003adf  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140003ae4  mov     edx, 20h ; ' '
0x140003ae9  mov     rcx, cs:WPP_GLOBAL_Control
0x140003af0  lea     r8, WPP_a4a5f05f0f7b31c3267dbefd3b846115_Traceguids
0x140003af7  mov     r9d, eax
0x140003afa  mov     [rsp+38h+var_18], 80070005h
0x140003b02  mov     rcx, [rcx+10h]
0x140003b06  call    WPP_SF_Dd
0x140003b0b  mov     ebx, 80070005h
0x140003b10  jmp     loc_140003BFB
0x140003b15  mov     rdx, [rsi+58h]; Buf2
0x140003b19  mov     rcx, rbx; Buf1
0x140003b1c  call    memcmp_0
0x140003b21  test    eax, eax
0x140003b23  jz      short loc_140003B50
0x140003b25  mov     rcx, cs:WPP_GLOBAL_Control
0x140003b2c  lea     rax, WPP_GLOBAL_Control
0x140003b33  cmp     rcx, rax
0x140003b36  jz      short loc_140003B0B
0x140003b38  test    byte ptr [rcx+1Ch], 8
0x140003b3c  jz      short loc_140003B0B
0x140003b3e  cmp     byte ptr [rcx+19h], 2
0x140003b42  jb      short loc_140003B0B
0x140003b44  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140003b49  mov     edx, 21h ; '!'
0x140003b4e  jmp     short loc_140003AE9
0x140003b50  test    rdi, rdi
0x140003b53  jnz     short loc_140003B8D
0x140003b55  mov     rcx, cs:WPP_GLOBAL_Control
0x140003b5c  lea     rax, WPP_GLOBAL_Control
0x140003b63  cmp     rcx, rax
0x140003b66  jz      loc_140003AA2
0x140003b6c  test    byte ptr [rcx+1Ch], 8
0x140003b70  jz      loc_140003AA2
0x140003b76  cmp     byte ptr [rcx+19h], 2
0x140003b7a  jb      loc_140003AA2
0x140003b80  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140003b85  lea     edx, [rdi+22h]
0x140003b88  jmp     loc_140003A80
0x140003b8d  cmp     qword ptr [rsi+38h], 0
0x140003b92  jz      short loc_140003BE6
0x140003b94  mov     rcx, cs:WPP_GLOBAL_Control
0x140003b9b  lea     rax, WPP_GLOBAL_Control
0x140003ba2  cmp     rcx, rax
0x140003ba5  jz      short loc_140003BDF
0x140003ba7  test    byte ptr [rcx+1Ch], 8
0x140003bab  jz      short loc_140003BDF
0x140003bad  cmp     byte ptr [rcx+19h], 2
0x140003bb1  jb      short loc_140003BDF
0x140003bb3  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140003bb8  mov     rcx, cs:WPP_GLOBAL_Control
0x140003bbf  lea     r8, WPP_a4a5f05f0f7b31c3267dbefd3b846115_Traceguids
0x140003bc6  mov     edx, 23h ; '#'
0x140003bcb  mov     [rsp+38h+var_18], 8000FFFFh
0x140003bd3  mov     r9d, eax
0x140003bd6  mov     rcx, [rcx+10h]
0x140003bda  call    WPP_SF_Dd
0x140003bdf  mov     ebx, 8000FFFFh
0x140003be4  jmp     short loc_140003BFB
0x140003be6  mov     [rsi+38h], rdi
0x140003bea  xor     ebx, ebx
0x140003bec  mov     rcx, [rdi]
0x140003bef  mov     rax, [rcx+8]
0x140003bf3  mov     rcx, rdi
0x140003bf6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003bfb  mov     rsi, [rsp+38h+arg_8]
0x140003c00  mov     eax, ebx
0x140003c02  mov     rbx, [rsp+38h+arg_0]
0x140003c07  add     rsp, 30h
0x140003c0b  pop     rdi
0x140003c0c  retn
```
