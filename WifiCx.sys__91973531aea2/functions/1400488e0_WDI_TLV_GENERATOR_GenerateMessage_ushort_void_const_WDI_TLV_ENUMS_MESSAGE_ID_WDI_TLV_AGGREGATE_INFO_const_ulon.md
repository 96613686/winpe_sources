# WDI_TLV::GENERATOR::GenerateMessage(ushort,void const *,WDI_TLV::ENUMS::MESSAGE_ID,WDI_TLV::_AGGREGATE_INFO const &,ulong,_TLV_CONTEXT const *,ulong *,uchar * *)

- ea: `0x1400488e0`
- end: `0x140048bd9`
- name: `?GenerateMessage@GENERATOR@WDI_TLV@@YAHGPEBXW4MESSAGE_ID@ENUMS@2@AEBU_AGGREGATE_INFO@2@KPEBU_TLV_CONTEXT@@PEAKPEAPEAE@Z`
- size: `761`
- prototype: `int __high(unsigned __int16, const void *, enum WDI_TLV::ENUMS::MESSAGE_ID, const struct WDI_TLV::_AGGREGATE_INFO *, unsigned int, const struct _TLV_CONTEXT *, unsigned int *, unsigned __int8 **)`
- caller_count: `39`
- callee_count: `9`
- tags: `file_ops`

## callers

- `0x14003fd4c`
- `0x14003fdb8`
- `0x14003fe24`
- `0x14003fe90`
- `0x14003fefc`
- `0x14003ff68`
- `0x14003ffd4`
- `0x140040048`
- `0x1400400b4`
- `0x140040120`
- `0x14004018c`
- `0x140040218`
- `0x140040284`
- `0x1400402f0`
- `0x14004035c`
- `0x1400403c8`
- `0x140040434`
- `0x1400404a0`
- `0x14004050c`
- `0x140040578`
- `0x1400405e4`
- `0x140040650`
- `0x1400406bc`
- `0x140040730`
- `0x140040798`
- `0x140040804`
- `0x140040870`
- `0x1400408e4`
- `0x140040958`
- `0x1400409cc`
- `0x140040a38`
- `0x140040aa4`
- `0x140040b10`
- `0x140040b7c`
- `0x140040be8`
- `0x140040c54`
- `0x140040cc0`
- `0x1400440c8`
- `0x140044110`

## callees

- `0x14000c940`
- `0x140016e30`
- `0x1400484c0`
- `0x1400488e0`
- `0x14004a55c`
- `0x14004a58c`
- `0x14004a5d0`
- `0x14004a624`
- `0x1400e0100`

## pseudocode

```c
__int64 __fastcall WDI_TLV::GENERATOR::GenerateMessage(
        unsigned __int16 a1,
        unsigned __int16 a2,
        unsigned __int16 a3,
        const void *a4,
        unsigned int a5,
        struct WDI_TLV::_AGGREGATE_INFO *a6,
        unsigned int *a7,
        _QWORD *a8)
{
  unsigned int v8; // r14d
  unsigned int Aggregate; // ebx
  unsigned int v13; // ebp
  _QWORD *v14; // rax
  _QWORD *v15; // rsi
  unsigned __int8 *v17[9]; // [rsp+30h] [rbp-48h] BYREF

  v8 = a3;
  LODWORD(v17[0]) = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
  {
    if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 156, WPP_2e582dc1a8f63b18f20a5c405b33b612_Traceguids);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
      WPP_SF_D(WPP_GLOBAL_Control->AttachedDevice, 157, WPP_2e582dc1a8f63b18f20a5c405b33b612_Traceguids, v8);
  }
  *a7 = 0;
  *a8 = 0;
  if ( a6 )
  {
    if ( *((_DWORD *)a6 + 2) >= 0x10000u )
    {
      Aggregate = WDI_TLV::GENERATOR::GenerateAggregate(
                    (WDI_TLV::GENERATOR *)a1,
                    a2,
                    a4,
                    a6,
                    (const struct _TLV_CONTEXT *)v17,
                    0,
                    v17[0]);
      if ( Aggregate )
      {
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
          return Aggregate;
        if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
          WPP_SF_DD(WPP_GLOBAL_Control->AttachedDevice, 160, WPP_2e582dc1a8f63b18f20a5c405b33b612_Traceguids);
      }
      else
      {
        v13 = LODWORD(v17[0]) + a5;
        if ( LODWORD(v17[0]) + a5 >= LODWORD(v17[0]) )
        {
          v14 = operator new(v13, *(_QWORD *)a6);
          v15 = v14;
          if ( v14 )
          {
            memset(v14, 0, v13);
            Aggregate = WDI_TLV::GENERATOR::GenerateAggregate(
                          (WDI_TLV::GENERATOR *)a1,
                          a2,
                          a4,
                          a6,
                          (const struct _TLV_CONTEXT *)v17,
                          (unsigned int *)((char *)v15 + a5),
                          v17[0]);
            if ( Aggregate )
            {
              if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
                WPP_SF_DD(WPP_GLOBAL_Control->AttachedDevice, 162, WPP_2e582dc1a8f63b18f20a5c405b33b612_Traceguids);
              operator delete(v15);
            }
            else
            {
              *a7 = v13;
              *a8 = v15;
            }
          }
          else
          {
            Aggregate = -1073741670;
          }
        }
        else
        {
          Aggregate = -1073741675;
          if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
            return Aggregate;
          if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
            WPP_SF_LdL(
              WPP_GLOBAL_Control->AttachedDevice,
              161,
              WPP_2e582dc1a8f63b18f20a5c405b33b612_Traceguids,
              LODWORD(v17[0]),
              a5,
              -1073741675);
        }
      }
    }
    else
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        WPP_SF_DD(WPP_GLOBAL_Control->AttachedDevice, 159, WPP_2e582dc1a8f63b18f20a5c405b33b612_Traceguids);
      Aggregate = -1071448020;
    }
  }
  else
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 158, WPP_2e582dc1a8f63b18f20a5c405b33b612_Traceguids);
    Aggregate = -1073741811;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
    WPP_SF_D(WPP_GLOBAL_Control->AttachedDevice, 163, WPP_2e582dc1a8f63b18f20a5c405b33b612_Traceguids, Aggregate);
  return Aggregate;
}

```

## disassembly

```asm
0x1400488e0  mov     rax, rsp
0x1400488e3  mov     [rax+18h], rbx
0x1400488e7  mov     [rax+20h], r9
0x1400488eb  mov     [rax+10h], rdx
0x1400488ef  mov     [rax+8], cx
0x1400488f3  push    rbp
0x1400488f4  push    rsi
0x1400488f5  push    rdi
0x1400488f6  push    r12
0x1400488f8  push    r13
0x1400488fa  push    r14
0x1400488fc  push    r15
0x1400488fe  sub     rsp, 40h
0x140048902  xor     r15d, r15d
0x140048905  movzx   r14d, r8w
0x140048909  mov     [rax-48h], r15d
0x14004890d  mov     rbx, r9
0x140048910  mov     rsi, rdx
0x140048913  movzx   ebp, cx
0x140048916  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14004891d  lea     rax, WPP_GLOBAL_Control
0x140048924  cmp     rcx, rax
0x140048927  jz      short loc_14004897C
0x140048929  cmp     byte ptr [rcx+29h], 5
0x14004892d  jb      short loc_14004894B
0x14004892f  mov     rcx, [rcx+18h]
0x140048933  lea     r8, WPP_2e582dc1a8f63b18f20a5c405b33b612_Traceguids
0x14004893a  mov     edx, 9Ch
0x14004893f  call    WPP_SF_
0x140048944  lea     rax, WPP_GLOBAL_Control
0x14004894b  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140048952  cmp     rcx, rax
0x140048955  jz      short loc_14004897C
0x140048957  cmp     byte ptr [rcx+29h], 5
0x14004895b  jb      short loc_14004897C
0x14004895d  mov     rcx, [rcx+18h]
0x140048961  lea     r8, WPP_2e582dc1a8f63b18f20a5c405b33b612_Traceguids
0x140048968  mov     r9d, r14d
0x14004896b  mov     edx, 9Dh
0x140048970  call    WPP_SF_D
0x140048975  lea     rax, WPP_GLOBAL_Control
0x14004897c  mov     r12, [rsp+78h+arg_30]
0x140048984  mov     r13, [rsp+78h+arg_38]
0x14004898c  mov     rdi, [rsp+78h+arg_28]
0x140048994  mov     [r12], r15d
0x140048998  mov     [r13+0], r15
0x14004899c  test    rdi, rdi
0x14004899f  jnz     short loc_1400489D2
0x1400489a1  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1400489a8  cmp     rcx, rax
0x1400489ab  jz      short loc_1400489C8
0x1400489ad  cmp     byte ptr [rcx+29h], 2
0x1400489b1  jb      short loc_1400489C8
0x1400489b3  mov     rcx, [rcx+18h]
0x1400489b7  lea     r8, WPP_2e582dc1a8f63b18f20a5c405b33b612_Traceguids
0x1400489be  mov     edx, 9Eh
0x1400489c3  call    WPP_SF_
0x1400489c8  mov     ebx, 0C000000Dh
0x1400489cd  jmp     loc_140048B8D
0x1400489d2  mov     r9d, [rdi+8]
0x1400489d6  mov     r8d, 10000h
0x1400489dc  cmp     r9d, r8d
0x1400489df  jnb     short loc_140048A17
0x1400489e1  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1400489e8  cmp     rcx, rax
0x1400489eb  jz      short loc_140048A0D
0x1400489ed  cmp     byte ptr [rcx+29h], 2
0x1400489f1  jb      short loc_140048A0D
0x1400489f3  mov     rcx, [rcx+18h]
0x1400489f7  mov     edx, 9Fh
0x1400489fc  mov     dword ptr [rsp+78h+var_58], r8d
0x140048a01  lea     r8, WPP_2e582dc1a8f63b18f20a5c405b33b612_Traceguids
0x140048a08  call    WPP_SF_DD
0x140048a0d  mov     ebx, 0C023002Ch
0x140048a12  jmp     loc_140048B8D
0x140048a17  lea     rax, [rsp+78h+var_48]
0x140048a1c  mov     [rsp+78h+var_50], r15; unsigned int *
0x140048a21  mov     r9, rdi; struct WDI_TLV::_AGGREGATE_INFO *
0x140048a24  mov     [rsp+78h+var_58], rax; struct _TLV_CONTEXT *
0x140048a29  mov     r8, rbx; void *
0x140048a2c  mov     rdx, rsi; unsigned __int16
0x140048a2f  movzx   ecx, bp; this
0x140048a32  call    ?GenerateAggregate@GENERATOR@WDI_TLV@@YAHGPEBXAEBU_AGGREGATE_INFO@2@PEBU_TLV_CONTEXT@@PEAIPEAE@Z; WDI_TLV::GENERATOR::GenerateAggregate(ushort,void const *,WDI_TLV::_AGGREGATE_INFO const &,_TLV_CONTEXT const *,uint *,uchar *)
0x140048a37  mov     ebx, eax
0x140048a39  test    eax, eax
0x140048a3b  jz      short loc_140048A7F
0x140048a3d  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140048a44  lea     rdi, WPP_GLOBAL_Control
0x140048a4b  cmp     rcx, rdi
0x140048a4e  jz      loc_140048BBE
0x140048a54  cmp     byte ptr [rcx+29h], 2
0x140048a58  jb      loc_140048B94
0x140048a5e  mov     rcx, [rcx+18h]
0x140048a62  lea     r8, WPP_2e582dc1a8f63b18f20a5c405b33b612_Traceguids
0x140048a69  mov     r9d, r14d
0x140048a6c  mov     dword ptr [rsp+78h+var_58], eax
0x140048a70  mov     edx, 0A0h
0x140048a75  call    WPP_SF_DD
0x140048a7a  jmp     loc_140048B94
0x140048a7f  mov     r9d, [rsp+78h+var_48]
0x140048a84  mov     r15d, [rsp+78h+arg_20]
0x140048a8c  lea     ebp, [r9+r15]
0x140048a90  cmp     ebp, r9d
0x140048a93  jnb     short loc_140048AE2
0x140048a95  mov     ebx, 0C0000095h
0x140048a9a  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140048aa1  lea     rdi, WPP_GLOBAL_Control
0x140048aa8  cmp     rcx, rdi
0x140048aab  jz      loc_140048BBE
0x140048ab1  cmp     byte ptr [rcx+29h], 2
0x140048ab5  jb      loc_140048B94
0x140048abb  mov     rcx, [rcx+18h]
0x140048abf  lea     r8, WPP_2e582dc1a8f63b18f20a5c405b33b612_Traceguids
0x140048ac6  mov     edx, 0A1h
0x140048acb  mov     dword ptr [rsp+78h+var_50], 0C0000095h
0x140048ad3  mov     dword ptr [rsp+78h+var_58], r15d
0x140048ad8  call    WPP_SF_LdL
0x140048add  jmp     loc_140048B94
0x140048ae2  mov     rdx, [rdi]; unsigned __int64
0x140048ae5  mov     ecx, ebp; Size
0x140048ae7  mov     ebx, ebp
0x140048ae9  call    ??2@YAPEAX_K0@Z; operator new(unsigned __int64,unsigned __int64)
0x140048aee  mov     rsi, rax
0x140048af1  test    rax, rax
0x140048af4  jnz     short loc_140048B00
0x140048af6  mov     ebx, 0C000009Ah
0x140048afb  jmp     loc_140048B8D
0x140048b00  mov     r8, rbx; Size
0x140048b03  xor     edx, edx; Val
0x140048b05  mov     rcx, rsi; void *
0x140048b08  call    memset
0x140048b0d  mov     r8, [rsp+78h+arg_18]; void *
0x140048b15  lea     rax, [rsi+r15]
0x140048b19  mov     rdx, qword ptr [rsp+78h+arg_8]; unsigned __int16
0x140048b21  mov     r9, rdi; struct WDI_TLV::_AGGREGATE_INFO *
0x140048b24  movzx   ecx, [rsp+78h+arg_0]; this
0x140048b2c  mov     [rsp+78h+var_50], rax; unsigned int *
0x140048b31  lea     rax, [rsp+78h+var_48]
0x140048b36  mov     [rsp+78h+var_58], rax; struct _TLV_CONTEXT *
0x140048b3b  call    ?GenerateAggregate@GENERATOR@WDI_TLV@@YAHGPEBXAEBU_AGGREGATE_INFO@2@PEBU_TLV_CONTEXT@@PEAIPEAE@Z; WDI_TLV::GENERATOR::GenerateAggregate(ushort,void const *,WDI_TLV::_AGGREGATE_INFO const &,_TLV_CONTEXT const *,uint *,uchar *)
0x140048b40  mov     ebx, eax
0x140048b42  test    eax, eax
0x140048b44  jz      short loc_140048B85
0x140048b46  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140048b4d  lea     rdi, WPP_GLOBAL_Control
0x140048b54  cmp     rcx, rdi
0x140048b57  jz      short loc_140048B7B
0x140048b59  cmp     byte ptr [rcx+29h], 2
0x140048b5d  jb      short loc_140048B7B
0x140048b5f  mov     rcx, [rcx+18h]
0x140048b63  lea     r8, WPP_2e582dc1a8f63b18f20a5c405b33b612_Traceguids
0x140048b6a  mov     r9d, r14d
0x140048b6d  mov     dword ptr [rsp+78h+var_58], eax
0x140048b71  mov     edx, 0A2h
0x140048b76  call    WPP_SF_DD
0x140048b7b  mov     rcx, rsi; void *
0x140048b7e  call    ??3@YAXPEAX@Z; operator delete(void *)
0x140048b83  jmp     short loc_140048B94
0x140048b85  mov     [r12], ebp
0x140048b89  mov     [r13+0], rsi
0x140048b8d  lea     rdi, WPP_GLOBAL_Control
0x140048b94  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140048b9b  cmp     rcx, rdi
0x140048b9e  jz      short loc_140048BBE
0x140048ba0  cmp     byte ptr [rcx+29h], 5
0x140048ba4  jb      short loc_140048BBE
0x140048ba6  mov     rcx, [rcx+18h]
0x140048baa  lea     r8, WPP_2e582dc1a8f63b18f20a5c405b33b612_Traceguids
0x140048bb1  mov     edx, 0A3h
0x140048bb6  mov     r9d, ebx
0x140048bb9  call    WPP_SF_D
0x140048bbe  mov     eax, ebx
0x140048bc0  mov     rbx, [rsp+78h+arg_10]
0x140048bc8  add     rsp, 40h
0x140048bcc  pop     r15
0x140048bce  pop     r14
0x140048bd0  pop     r13
0x140048bd2  pop     r12
0x140048bd4  pop     rdi
0x140048bd5  pop     rsi
0x140048bd6  pop     rbp
0x140048bd7  retn
```
