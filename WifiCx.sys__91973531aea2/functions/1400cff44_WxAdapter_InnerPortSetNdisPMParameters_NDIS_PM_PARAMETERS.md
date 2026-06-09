# WxAdapter::InnerPortSetNdisPMParameters(_NDIS_PM_PARAMETERS *)

- ea: `0x1400cff44`
- end: `0x1400d00e4`
- name: `?InnerPortSetNdisPMParameters@WxAdapter@@AEAAXPEAU_NDIS_PM_PARAMETERS@@@Z`
- size: `416`
- prototype: `void(WxAdapter *__hidden this, struct _NDIS_PM_PARAMETERS *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1400d0150`

## callees

- `0x14000c778`
- `0x14000d054`
- `0x1400cff44`
- `0x1400dfd00`
- `0x1400dfe00`

## import_xrefs

- `ntoskrnl!RtlCompareMemory` at `0x1400d000d`
- `ntoskrnl!RtlCompareMemory` at `0x1400d000d`

## pseudocode

```c
void __fastcall WxAdapter::InnerPortSetNdisPMParameters(WxAdapter *this, struct _NDIS_PM_PARAMETERS *a2)
{
  struct _NDIS_PM_PARAMETERS *v2; // rsi
  size_t Size; // r8
  __int64 v5; // [rsp+28h] [rbp-50h]
  _BYTE v6[24]; // [rsp+30h] [rbp-48h] BYREF

  memset(v6, 0, 20);
  v2 = a2;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
    && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
  {
    LOBYTE(a2) = 5;
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      (_DWORD)a2,
      1,
      21,
      (__int64)WPP_3742f7b8aa593665a28f1ce7634f5781_Traceguids);
  }
  if ( !*((_DWORD *)this + 134) )
  {
    Size = 20;
    *((_OWORD *)this + 57) = 0;
    *((_DWORD *)this + 232) = 0;
    if ( v2->Header.Size < 0x14u )
      Size = v2->Header.Size;
    memmove((char *)this + 912, v2, Size);
    if ( RtlCompareMemory(&v6[4], (char *)this + 916, 0x10u) == 16 )
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(a2) = 4;
        WPP_RECORDER_SF_(
          WPP_GLOBAL_Control->DeviceExtension,
          (_DWORD)a2,
          1,
          22,
          (__int64)WPP_3742f7b8aa593665a28f1ce7634f5781_Traceguids);
      }
      *((_BYTE *)this + 932) = 0;
    }
    else
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(a2) = 4;
        WPP_RECORDER_SF_d(
          WPP_GLOBAL_Control->DeviceExtension,
          (_DWORD)a2,
          1,
          23,
          (__int64)WPP_3742f7b8aa593665a28f1ce7634f5781_Traceguids,
          *((_DWORD *)this + 229),
          *(_OWORD *)v6,
          *(_QWORD *)&v6[16]);
      }
      *((_BYTE *)this + 932) = 1;
    }
  }
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
    && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
  {
    LODWORD(v5) = 0;
    LOBYTE(a2) = 5;
    WPP_RECORDER_SF_d(
      WPP_GLOBAL_Control->DeviceExtension,
      (_DWORD)a2,
      1,
      24,
      (__int64)WPP_3742f7b8aa593665a28f1ce7634f5781_Traceguids,
      v5);
  }
}

```

## disassembly

```asm
0x1400cff44  mov     [rsp+arg_10], rbx
0x1400cff49  push    rbp
0x1400cff4a  push    rsi
0x1400cff4b  push    rdi
0x1400cff4c  push    r12
0x1400cff4e  push    r15
0x1400cff50  sub     rsp, 50h
0x1400cff54  mov     rax, cs:__security_cookie
0x1400cff5b  xor     rax, rsp
0x1400cff5e  mov     [rsp+78h+var_30], rax
0x1400cff63  xor     ebp, ebp
0x1400cff65  xorps   xmm0, xmm0
0x1400cff68  xor     eax, eax
0x1400cff6a  mov     [rsp+78h+var_48], bpl
0x1400cff6f  movups  [rsp+78h+Source1], xmm0
0x1400cff74  mov     dword ptr [rsp+78h+Source1+0Fh], eax
0x1400cff78  mov     rsi, rdx
0x1400cff7b  mov     rbx, rcx
0x1400cff7e  lea     r15, WPP_RECORDER_INITIALIZED
0x1400cff85  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x1400cff8c  lea     r12, WPP_3742f7b8aa593665a28f1ce7634f5781_Traceguids
0x1400cff93  jz      short loc_1400CFFC2
0x1400cff95  mov     rcx, cs:WPP_GLOBAL_Control
0x1400cff9c  cmp     byte ptr [rcx+29h], 5
0x1400cffa0  jnb     short loc_1400CFFA8
0x1400cffa2  cmp     [rcx+48h], bp
0x1400cffa6  jz      short loc_1400CFFC2
0x1400cffa8  mov     rcx, [rcx+40h]
0x1400cffac  mov     r9d, 15h
0x1400cffb2  mov     dl, 5
0x1400cffb4  mov     [rsp+78h+var_58], r12
0x1400cffb9  lea     r8d, [r9-14h]
0x1400cffbd  call    WPP_RECORDER_SF_
0x1400cffc2  cmp     [rbx+218h], ebp
0x1400cffc8  jnz     loc_1400D0088
0x1400cffce  xor     eax, eax
0x1400cffd0  lea     rdi, [rbx+390h]
0x1400cffd7  xorps   xmm0, xmm0
0x1400cffda  mov     r8d, 14h
0x1400cffe0  movups  xmmword ptr [rdi], xmm0
0x1400cffe3  mov     [rdi+10h], eax
0x1400cffe6  movzx   eax, word ptr [rsi+2]
0x1400cffea  cmp     ax, r8w
0x1400cffee  jnb     short loc_1400CFFF3
0x1400cfff0  mov     r8d, eax; Size
0x1400cfff3  mov     rdx, rsi; Src
0x1400cfff6  mov     rcx, rdi; void *
0x1400cfff9  call    memmove
0x1400cfffe  mov     r8d, 10h; Length
0x1400d0004  lea     rdx, [rdi+4]; Source2
0x1400d0008  lea     rcx, [rsp+78h+Source1+3]; Source1
0x1400d000d  call    cs:__imp_RtlCompareMemory
0x1400d0014  nop     dword ptr [rax+rax+00h]
0x1400d0019  cmp     rax, 10h
0x1400d001d  jnz     short loc_1400D0050
0x1400d001f  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x1400d0026  jz      short loc_1400D0047
0x1400d0028  mov     rcx, cs:WPP_GLOBAL_Control
0x1400d002f  lea     r9d, [rax+6]
0x1400d0033  lea     r8d, [rax-0Fh]
0x1400d0037  mov     [rsp+78h+var_58], r12
0x1400d003c  mov     dl, 4
0x1400d003e  mov     rcx, [rcx+40h]
0x1400d0042  call    WPP_RECORDER_SF_
0x1400d0047  mov     [rbx+3A4h], bpl
0x1400d004e  jmp     short loc_1400D0088
0x1400d0050  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x1400d0057  jz      short loc_1400D0081
0x1400d0059  mov     rcx, cs:WPP_GLOBAL_Control
0x1400d0060  mov     r9d, 17h
0x1400d0066  mov     eax, [rdi+4]
0x1400d0069  mov     dl, 4
0x1400d006b  mov     dword ptr [rsp+78h+var_50], eax
0x1400d006f  mov     [rsp+78h+var_58], r12
0x1400d0074  mov     rcx, [rcx+40h]
0x1400d0078  lea     r8d, [r9-16h]
0x1400d007c  call    WPP_RECORDER_SF_d
0x1400d0081  mov     byte ptr [rbx+3A4h], 1
0x1400d0088  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x1400d008f  jz      short loc_1400D00C2
0x1400d0091  mov     rcx, cs:WPP_GLOBAL_Control
0x1400d0098  cmp     byte ptr [rcx+29h], 5
0x1400d009c  jnb     short loc_1400D00A4
0x1400d009e  cmp     [rcx+48h], bp
0x1400d00a2  jz      short loc_1400D00C2
0x1400d00a4  mov     rcx, [rcx+40h]
0x1400d00a8  mov     r9d, 18h
0x1400d00ae  mov     dword ptr [rsp+78h+var_50], ebp
0x1400d00b2  mov     dl, 5
0x1400d00b4  mov     [rsp+78h+var_58], r12
0x1400d00b9  lea     r8d, [r9-17h]
0x1400d00bd  call    WPP_RECORDER_SF_d
0x1400d00c2  mov     rcx, [rsp+78h+var_30]
0x1400d00c7  xor     rcx, rsp; StackCookie
0x1400d00ca  call    __security_check_cookie
0x1400d00cf  mov     rbx, [rsp+78h+arg_10]
0x1400d00d7  add     rsp, 50h
0x1400d00db  pop     r15
0x1400d00dd  pop     r12
0x1400d00df  pop     rdi
0x1400d00e0  pop     rsi
0x1400d00e1  pop     rbp
0x1400d00e2  retn
```
