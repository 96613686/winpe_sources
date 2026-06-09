# MultiLinkIEHelpers::ParseMultiLinkIE(ulong,DOT11_INFO_ELEMENT const *,MultiLinkIEHelpers::MULTILINK_IE_INFO *)

- ea: `0x1400afad0`
- end: `0x1400afd5e`
- name: `?ParseMultiLinkIE@MultiLinkIEHelpers@@YAHKPEBUDOT11_INFO_ELEMENT@@PEAUMULTILINK_IE_INFO@1@@Z`
- size: `654`
- prototype: `int(MultiLinkIEHelpers *__hidden this, unsigned int, const struct DOT11_INFO_ELEMENT *, struct MultiLinkIEHelpers::MULTILINK_IE_INFO *)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x1400a9804`

## callees

- `0x140009420`
- `0x14000c940`
- `0x140024a20`
- `0x1400347b4`
- `0x140050574`
- `0x1400684cc`
- `0x1400afad0`
- `0x1400afd64`
- `0x1400aff0c`
- `0x1400da718`

## pseudocode

```c
__int64 __fastcall MultiLinkIEHelpers::ParseMultiLinkIE(
        MultiLinkIEHelpers *this,
        __int64 a2,
        const struct DOT11_INFO_ELEMENT *a3,
        struct MultiLinkIEHelpers::MULTILINK_IE_INFO *a4)
{
  unsigned int v5; // ebx
  __int64 result; // rax
  int v8; // edx
  int v9; // r8d
  unsigned int v10; // esi
  unsigned int v11; // ecx
  unsigned int v12; // ebx
  __int64 v13; // rdi
  int v14; // ebp
  unsigned int v15; // ebp
  unsigned int ReassembledIE; // eax
  int v17; // edx
  int v18; // r8d
  char v19; // r15
  char v20; // si
  char *v21; // rax
  int v22; // edx
  int v23; // r8d
  char *v24; // r14
  struct MultiLinkIEHelpers::MULTILINK_IE_INFO *v25; // r9
  char *v26; // rcx
  int v27; // edx
  int v28; // r8d
  MultiLinkIEHelpers *v29; // [rsp+80h] [rbp+8h] BYREF
  unsigned int v30; // [rsp+88h] [rbp+10h] BYREF

  v5 = (unsigned int)this;
  result = MultiLinkIEHelpers::ParseMultiLinkIECommonInfo(
             (MultiLinkIEHelpers *)(unsigned int)((_DWORD)this - 2),
             (int)a2 + 2,
             a3,
             a4);
  v10 = result;
  if ( !(_DWORD)result )
  {
    v11 = *(unsigned __int8 *)(a2 + 5) + 5;
    if ( v5 >= v11 )
    {
      v12 = v5 - v11;
      v13 = a2 + v11;
      if ( v12 >= 2 )
      {
        while ( 1 )
        {
          v14 = *(unsigned __int8 *)(v13 + 1);
          v30 = 0;
          LODWORD(v29) = 0;
          v15 = v14 + 2;
          ReassembledIE = Dot11GetReassembledIE(254, v12, (unsigned __int8 *)v13, &v30, (unsigned int *)&v29, 0);
          v19 = v30;
          v10 = ReassembledIE;
          if ( !ReassembledIE && v30 )
            v15 = v30;
          if ( v12 < v15 )
            break;
          if ( !*(_BYTE *)v13 )
          {
            v20 = (char)v29;
            v21 = (char *)operator new((unsigned int)v29);
            v24 = v21;
            if ( !v21 )
            {
              if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
              {
                LOBYTE(v22) = 2;
                WPP_RECORDER_SF_dDd(
                  WPP_GLOBAL_Control->DeviceExtension,
                  v22,
                  v23,
                  47,
                  (__int64)&WPP_54405addb41d3096058a1ee6dddc76fe_Traceguids,
                  *(_BYTE *)(v13 + 1),
                  v20,
                  v19);
              }
              return 3221225626LL;
            }
            v10 = Dot11GetReassembledIE(254, v12, (unsigned __int8 *)v13, &v30, (unsigned int *)&v29, v21);
            if ( v10 )
            {
              MicrosoftTelemetryAssertTriggeredNoArgsKM();
              if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
              {
                LOBYTE(v27) = 2;
                WPP_RECORDER_SF_dDd(
                  WPP_GLOBAL_Control->DeviceExtension,
                  v27,
                  v28,
                  48,
                  (__int64)&WPP_54405addb41d3096058a1ee6dddc76fe_Traceguids,
                  *(_BYTE *)(v13 + 1),
                  (char)v29,
                  v30);
              }
              v26 = v24;
LABEL_21:
              operator delete(v26);
              return v10;
            }
            v10 = MultiLinkIEHelpers::ParseMultiLinkIEPerStaProfile(
                    (MultiLinkIEHelpers *)(unsigned int)v29,
                    (unsigned int)v24,
                    a3,
                    v25);
            v26 = v24;
            if ( v10 )
              goto LABEL_21;
            operator delete(v24);
          }
          v12 -= v15;
          if ( v12 < 2 )
            return v10;
          v13 += v15;
        }
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          LOBYTE(v17) = 2;
          WPP_RECORDER_SF_dddd(
            WPP_GLOBAL_Control->DeviceExtension,
            v17,
            v18,
            46,
            (__int64)&WPP_54405addb41d3096058a1ee6dddc76fe_Traceguids,
            *(_BYTE *)v13,
            *(_BYTE *)(v13 + 1),
            v15,
            v12);
        }
      }
      return v10;
    }
    else
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v8) = 2;
        WPP_RECORDER_SF_Ld(
          WPP_GLOBAL_Control->DeviceExtension,
          v8,
          v9,
          45,
          (__int64)&WPP_54405addb41d3096058a1ee6dddc76fe_Traceguids,
          v5,
          v11);
      }
      return 3221225485LL;
    }
  }
  return result;
}

```

## disassembly

```asm
0x1400afad0  mov     [rsp+arg_10], rbx
0x1400afad5  mov     [rsp+arg_18], rbp
0x1400afada  push    rsi
0x1400afadb  push    rdi
0x1400afadc  push    r12
0x1400afade  push    r14
0x1400afae0  push    r15
0x1400afae2  sub     rsp, 50h
0x1400afae6  mov     rbp, rdx
0x1400afae9  mov     ebx, ecx
0x1400afaeb  add     ecx, 0FFFFFFFEh; this
0x1400afaee  add     rdx, 2; unsigned int
0x1400afaf2  mov     r12, r8
0x1400afaf5  call    ?ParseMultiLinkIECommonInfo@MultiLinkIEHelpers@@YAHKPEBUDOT11_MLO_MULTILINK_ELEMENT@@PEAUMULTILINK_IE_INFO@1@@Z; MultiLinkIEHelpers::ParseMultiLinkIECommonInfo(ulong,DOT11_MLO_MULTILINK_ELEMENT const *,MultiLinkIEHelpers::MULTILINK_IE_INFO *)
0x1400afafa  mov     esi, eax
0x1400afafc  test    eax, eax
0x1400afafe  jnz     loc_1400AFD44
0x1400afb04  movzx   ecx, byte ptr [rbp+5]
0x1400afb08  add     ecx, 5
0x1400afb0b  cmp     ebx, ecx
0x1400afb0d  jnb     short loc_1400AFB53
0x1400afb0f  lea     rax, WPP_RECORDER_INITIALIZED
0x1400afb16  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400afb1d  jz      short loc_1400AFB49
0x1400afb1f  mov     [rsp+78h+var_48], ecx
0x1400afb23  lea     rax, WPP_54405addb41d3096058a1ee6dddc76fe_Traceguids
0x1400afb2a  mov     rcx, cs:WPP_GLOBAL_Control
0x1400afb31  lea     r9d, [rsi+2Dh]
0x1400afb35  mov     dword ptr [rsp+78h+var_50], ebx
0x1400afb39  mov     dl, 2
0x1400afb3b  mov     [rsp+78h+var_58], rax
0x1400afb40  mov     rcx, [rcx+40h]
0x1400afb44  call    WPP_RECORDER_SF_Ld
0x1400afb49  mov     eax, 0C000000Dh
0x1400afb4e  jmp     loc_1400AFD44
0x1400afb53  mov     edi, ecx
0x1400afb55  sub     ebx, ecx
0x1400afb57  add     rdi, rbp
0x1400afb5a  cmp     ebx, 2
0x1400afb5d  jb      loc_1400AFD42
0x1400afb63  movzx   ebp, byte ptr [rdi+1]
0x1400afb67  lea     rax, [rsp+78h+arg_0]
0x1400afb6f  mov     [rsp+78h+var_50], 0
0x1400afb78  lea     r9, [rsp+78h+arg_8]
0x1400afb80  mov     r8, rdi
0x1400afb83  mov     [rsp+78h+var_58], rax
0x1400afb88  mov     edx, ebx
0x1400afb8a  mov     [rsp+78h+arg_8], 0
0x1400afb95  mov     cl, 0FEh
0x1400afb97  mov     dword ptr [rsp+78h+arg_0], 0
0x1400afba2  add     ebp, 2
0x1400afba5  call    Dot11GetReassembledIE
0x1400afbaa  mov     r15d, [rsp+78h+arg_8]
0x1400afbb2  mov     esi, eax
0x1400afbb4  test    eax, eax
0x1400afbb6  jnz     short loc_1400AFBBF
0x1400afbb8  test    r15d, r15d
0x1400afbbb  cmovnz  ebp, r15d
0x1400afbbf  cmp     ebx, ebp
0x1400afbc1  jb      loc_1400AFCF7
0x1400afbc7  cmp     byte ptr [rdi], 0
0x1400afbca  jnz     short loc_1400AFC32
0x1400afbcc  mov     esi, dword ptr [rsp+78h+arg_0]
0x1400afbd3  mov     ecx, esi; unsigned __int64
0x1400afbd5  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1400afbda  mov     r14, rax
0x1400afbdd  test    rax, rax
0x1400afbe0  jz      loc_1400AFCAB
0x1400afbe6  mov     [rsp+78h+var_50], rax
0x1400afbeb  lea     r9, [rsp+78h+arg_8]
0x1400afbf3  lea     rax, [rsp+78h+arg_0]
0x1400afbfb  mov     r8, rdi
0x1400afbfe  mov     edx, ebx
0x1400afc00  mov     [rsp+78h+var_58], rax
0x1400afc05  mov     cl, 0FEh
0x1400afc07  call    Dot11GetReassembledIE
0x1400afc0c  mov     esi, eax
0x1400afc0e  test    eax, eax
0x1400afc10  jnz     short loc_1400AFC47
0x1400afc12  mov     ecx, dword ptr [rsp+78h+arg_0]; this
0x1400afc19  mov     r8, r12; struct DOT11_MLO_MULTILINK_PER_STA_PROFILE_HEADER *
0x1400afc1c  mov     rdx, r14; unsigned int
0x1400afc1f  call    ?ParseMultiLinkIEPerStaProfile@MultiLinkIEHelpers@@YAHKPEAUDOT11_MLO_MULTILINK_PER_STA_PROFILE_HEADER@@PEAUMULTILINK_IE_INFO@1@@Z; MultiLinkIEHelpers::ParseMultiLinkIEPerStaProfile(ulong,DOT11_MLO_MULTILINK_PER_STA_PROFILE_HEADER *,MultiLinkIEHelpers::MULTILINK_IE_INFO *)
0x1400afc24  mov     esi, eax
0x1400afc26  mov     rcx, r14; void *
0x1400afc29  test    eax, eax
0x1400afc2b  jnz     short loc_1400AFCA1
0x1400afc2d  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1400afc32  sub     ebx, ebp
0x1400afc34  cmp     ebx, 2
0x1400afc37  jb      loc_1400AFD42
0x1400afc3d  mov     eax, ebp
0x1400afc3f  add     rdi, rax
0x1400afc42  jmp     loc_1400AFB63
0x1400afc47  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x1400afc4c  lea     rax, WPP_RECORDER_INITIALIZED
0x1400afc53  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400afc5a  jz      short loc_1400AFC9E
0x1400afc5c  mov     eax, [rsp+78h+arg_8]
0x1400afc63  mov     r9d, 30h ; '0'
0x1400afc69  movzx   ecx, byte ptr [rdi+1]
0x1400afc6d  mov     dl, 2
0x1400afc6f  mov     [rsp+78h+var_40], eax
0x1400afc73  mov     eax, dword ptr [rsp+78h+arg_0]
0x1400afc7a  mov     [rsp+78h+var_48], eax
0x1400afc7e  lea     rax, WPP_54405addb41d3096058a1ee6dddc76fe_Traceguids
0x1400afc85  mov     dword ptr [rsp+78h+var_50], ecx
0x1400afc89  mov     rcx, cs:WPP_GLOBAL_Control
0x1400afc90  mov     [rsp+78h+var_58], rax
0x1400afc95  mov     rcx, [rcx+40h]
0x1400afc99  call    WPP_RECORDER_SF_dDd
0x1400afc9e  mov     rcx, r14; void *
0x1400afca1  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1400afca6  jmp     loc_1400AFD42
0x1400afcab  lea     rax, WPP_RECORDER_INITIALIZED
0x1400afcb2  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400afcb9  jz      short loc_1400AFCF0
0x1400afcbb  movzx   eax, byte ptr [rdi+1]
0x1400afcbf  mov     r9d, 2Fh ; '/'
0x1400afcc5  mov     rcx, cs:WPP_GLOBAL_Control
0x1400afccc  mov     dl, 2
0x1400afcce  mov     [rsp+78h+var_40], r15d
0x1400afcd3  mov     [rsp+78h+var_48], esi
0x1400afcd7  mov     dword ptr [rsp+78h+var_50], eax
0x1400afcdb  lea     rax, WPP_54405addb41d3096058a1ee6dddc76fe_Traceguids
0x1400afce2  mov     rcx, [rcx+40h]
0x1400afce6  mov     [rsp+78h+var_58], rax
0x1400afceb  call    WPP_RECORDER_SF_dDd
0x1400afcf0  mov     eax, 0C000009Ah
0x1400afcf5  jmp     short loc_1400AFD44
0x1400afcf7  lea     rax, WPP_RECORDER_INITIALIZED
0x1400afcfe  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400afd05  jz      short loc_1400AFD42
0x1400afd07  movzx   eax, byte ptr [rdi+1]
0x1400afd0b  mov     r9d, 2Eh ; '.'
0x1400afd11  movzx   ecx, byte ptr [rdi]
0x1400afd14  mov     dl, 2
0x1400afd16  mov     [rsp+78h+var_38], ebx
0x1400afd1a  mov     [rsp+78h+var_40], ebp
0x1400afd1e  mov     [rsp+78h+var_48], eax
0x1400afd22  lea     rax, WPP_54405addb41d3096058a1ee6dddc76fe_Traceguids
0x1400afd29  mov     dword ptr [rsp+78h+var_50], ecx
0x1400afd2d  mov     rcx, cs:WPP_GLOBAL_Control
0x1400afd34  mov     [rsp+78h+var_58], rax
0x1400afd39  mov     rcx, [rcx+40h]
0x1400afd3d  call    WPP_RECORDER_SF_dddd
0x1400afd42  mov     eax, esi
0x1400afd44  lea     r11, [rsp+78h+var_28]
0x1400afd49  mov     rbx, [r11+40h]
0x1400afd4d  mov     rbp, [r11+48h]
0x1400afd51  mov     rsp, r11
0x1400afd54  pop     r15
0x1400afd56  pop     r14
0x1400afd58  pop     r12
0x1400afd5a  pop     rdi
0x1400afd5b  pop     rsi
0x1400afd5c  retn
```
