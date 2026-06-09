# MbbIpProcessRouteEntry(_MBB_IPADDRESS_ENTRY *,ulong,_MBB_IPADDRESS_ENTRY *,ulong,_MBB_IPADDRESS_ENTRY *,ulong,_MIB_IPFORWARD_ROW2 *)

- ea: `0x1400448c8`
- end: `0x140044bfb`
- name: `?MbbIpProcessRouteEntry@@YAEPEAU_MBB_IPADDRESS_ENTRY@@K0K0KPEAU_MIB_IPFORWARD_ROW2@@@Z`
- size: `819`
- prototype: `unsigned __int8 __fastcall(struct _MBB_IPADDRESS_ENTRY *, unsigned int, struct _MBB_IPADDRESS_ENTRY *, unsigned int, struct _MBB_IPADDRESS_ENTRY *, unsigned int, MIB_IPFORWARD_ROW2 *Row)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140042e30`

## callees

- `0x14004323c`
- `0x1400448c8`
- `0x140046378`
- `0x1400466a4`
- `0x1400469e8`
- `0x140047e50`

## import_xrefs

- `ntoskrnl!RtlCompareMemory` at `0x14004494d`
- `ntoskrnl!RtlCompareMemory` at `0x1400449db`
- `ntoskrnl!RtlCompareMemory` at `0x14004494d`
- `ntoskrnl!RtlCompareMemory` at `0x1400449db`
- `NETIO!DeleteIpForwardEntry2` at `0x140044b8c`
- `NETIO!DeleteIpForwardEntry2` at `0x140044b8c`

## pseudocode

```c
unsigned __int8 __fastcall MbbIpProcessRouteEntry(
        struct _MBB_IPADDRESS_ENTRY *a1,
        unsigned int a2,
        struct _MBB_IPADDRESS_ENTRY *a3,
        unsigned int a4,
        struct _MBB_IPADDRESS_ENTRY *a5,
        unsigned int a6,
        MIB_IPFORWARD_ROW2 *Row)
{
  char v7; // si
  ADDRESS_FAMILY sin_family; // ax
  int v13; // edx
  int v14; // r8d
  int v16; // edx
  int v17; // r8d
  ADDRESS_FAMILY v18; // ax
  ADDRESS_FAMILY v19; // ax
  NTSTATUS v20; // eax
  int v21; // edx
  int v22; // r8d
  unsigned int v23; // [rsp+40h] [rbp-20h] BYREF
  char Source2; // [rsp+44h] [rbp-1Ch] BYREF
  __int16 v25; // [rsp+45h] [rbp-1Bh]
  char v26; // [rsp+47h] [rbp-19h]
  char v27; // [rsp+48h] [rbp-18h] BYREF
  __int64 v28; // [rsp+49h] [rbp-17h]
  int v29; // [rsp+51h] [rbp-Fh]
  __int16 v30; // [rsp+55h] [rbp-Bh]
  char v31; // [rsp+57h] [rbp-9h]

  v7 = 0;
  v25 = 0;
  v26 = 0;
  v28 = 0;
  v29 = 0;
  v30 = 0;
  v31 = 0;
  sin_family = Row->DestinationPrefix.Prefix.Ipv4.sin_family;
  v23 = 0;
  Source2 = 0;
  v27 = 0;
  if ( sin_family != 2 )
  {
    if ( sin_family != 23
      || !Row->DestinationPrefix.PrefixLength
      && RtlCompareMemory(&Row->DestinationPrefix.Prefix.si_family + 4, &v27, 0x10u) == 16 )
    {
      goto LABEL_4;
    }
    return 0;
  }
  if ( Row->DestinationPrefix.PrefixLength
    || RtlCompareMemory(&Row->DestinationPrefix.Prefix.si_family + 2, &Source2, 4u) != 4 )
  {
    return 0;
  }
LABEL_4:
  if ( (unsigned int)MbbIpFindRouteInTable(a1, a2, Row, &v23) )
  {
    if ( (unsigned int)MbbIpFindRouteInTable(a3, a4, Row, &v23)
      && (unsigned int)MbbIpFindRouteInTable(a5, a6, Row, &v23) )
    {
      if ( Row->Origin == NlroManual )
      {
        v18 = Row->NextHop.Ipv4.sin_family;
        if ( v18 == 2 )
        {
          if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            WPP_RECORDER_SF_i_IPV4_(WPP_GLOBAL_Control->DeviceExtension, v16, v17, 83);
        }
        else if ( v18 == 23 && WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          WPP_RECORDER_SF_i_IPV6_(WPP_GLOBAL_Control->DeviceExtension, v16, v17, 84);
        }
        return 1;
      }
    }
    else
    {
      v19 = Row->NextHop.Ipv4.sin_family;
      if ( v19 == 2 )
      {
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          WPP_RECORDER_SF_i_IPV4_(WPP_GLOBAL_Control->DeviceExtension, v16, v17, 80);
      }
      else if ( v19 == 23 && WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        WPP_RECORDER_SF_i_IPV6_(WPP_GLOBAL_Control->DeviceExtension, v16, v17, 81);
      }
      v20 = DeleteIpForwardEntry2(Row);
      if ( v20 && WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        WPP_RECORDER_SF_id(
          WPP_GLOBAL_Control->DeviceExtension,
          v21,
          v22,
          82,
          (__int64)WPP_f53708f2277a3aabca584f524242a299_Traceguids,
          Row->InterfaceLuid.Value,
          v20);
    }
  }
  else
  {
    if ( Row->NextHop.Ipv4.sin_family == 2 )
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        WPP_RECORDER_SF_i_IPV4_(WPP_GLOBAL_Control->DeviceExtension, v13, v14, 78);
    }
    else if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      WPP_RECORDER_SF_i_IPV6_(WPP_GLOBAL_Control->DeviceExtension, v13, v14, 79);
    }
    *((_DWORD *)a1 + 6 * v23) |= 2u;
  }
  return v7;
}

```

## disassembly

```asm
0x1400448c8  mov     [rsp-38h+arg_8], rbx
0x1400448cd  push    rbp
0x1400448ce  push    rsi
0x1400448cf  push    rdi
0x1400448d0  push    r12
0x1400448d2  push    r13
0x1400448d4  push    r14
0x1400448d6  push    r15
0x1400448d8  mov     rbp, rsp
0x1400448db  sub     rsp, 60h
0x1400448df  mov     rax, cs:__security_cookie
0x1400448e6  xor     rax, rsp
0x1400448e9  mov     [rbp+var_8], rax
0x1400448ed  mov     rbx, [rbp+Row]
0x1400448f1  xor     eax, eax
0x1400448f3  mov     r15, [rbp+arg_20]
0x1400448f7  xor     esi, esi
0x1400448f9  mov     r14, rcx
0x1400448fc  mov     [rbp+var_1B], ax
0x140044900  mov     [rbp+var_19], al
0x140044903  mov     edi, edx
0x140044905  mov     [rbp+var_17], rax
0x140044909  mov     r12d, r9d
0x14004490c  mov     [rbp+var_F], eax
0x14004490f  lea     ecx, [rsi+2]
0x140044912  mov     [rbp+var_B], ax
0x140044916  lea     edx, [rsi+17h]
0x140044919  mov     [rbp+var_9], al
0x14004491c  mov     r13, r8
0x14004491f  movzx   eax, word ptr [rbx+0Ch]
0x140044923  mov     [rbp+var_20], esi
0x140044926  mov     [rbp+Source2], sil
0x14004492a  mov     [rbp+var_18], sil
0x14004492e  cmp     cx, ax
0x140044931  jnz     loc_1400449C2
0x140044937  cmp     [rbx+28h], sil
0x14004493b  jnz     loc_1400449F1
0x140044941  lea     rcx, [rbx+10h]; Source1
0x140044945  lea     r8d, [rsi+4]; Length
0x140044949  lea     rdx, [rbp+Source2]; Source2
0x14004494d  call    cs:__imp_RtlCompareMemory
0x140044954  nop     dword ptr [rax+rax+00h]
0x140044959  cmp     rax, 4
0x14004495d  jnz     loc_1400449F1
0x140044963  lea     r9, [rbp+var_20]; unsigned int *
0x140044967  mov     r8, rbx; struct _MIB_IPFORWARD_ROW2 *
0x14004496a  mov     edx, edi; unsigned int
0x14004496c  mov     rcx, r14; struct _MBB_IPADDRESS_ENTRY *
0x14004496f  call    ?MbbIpFindRouteInTable@@YAHPEAU_MBB_IPADDRESS_ENTRY@@KPEAU_MIB_IPFORWARD_ROW2@@PEAK@Z; MbbIpFindRouteInTable(_MBB_IPADDRESS_ENTRY *,ulong,_MIB_IPFORWARD_ROW2 *,ulong *)
0x140044974  test    eax, eax
0x140044976  jnz     loc_140044A3F
0x14004497c  lea     r15d, [rax+2]
0x140044980  cmp     r15w, [rbx+2Ch]
0x140044985  jnz     short loc_1400449F8
0x140044987  lea     rdi, WPP_RECORDER_INITIALIZED
0x14004498e  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x140044995  jz      loc_140044A2F
0x14004499b  mov     rcx, cs:WPP_GLOBAL_Control
0x1400449a2  lea     rax, [rbx+30h]
0x1400449a6  mov     [rsp+60h+var_30], rax
0x1400449ab  lea     r9d, [r15+4Ch]
0x1400449af  mov     rax, [rbx]
0x1400449b2  mov     [rsp+60h+var_38], rax
0x1400449b7  mov     rcx, [rcx+40h]
0x1400449bb  call    WPP_RECORDER_SF_i_IPV4_
0x1400449c0  jmp     short loc_140044A2F
0x1400449c2  cmp     dx, ax
0x1400449c5  jnz     short loc_140044963
0x1400449c7  cmp     [rbx+28h], sil
0x1400449cb  jnz     short loc_1400449F1
0x1400449cd  lea     rcx, [rbx+14h]; Source1
0x1400449d1  mov     r8d, 10h; Length
0x1400449d7  lea     rdx, [rbp+var_18]; Source2
0x1400449db  call    cs:__imp_RtlCompareMemory
0x1400449e2  nop     dword ptr [rax+rax+00h]
0x1400449e7  cmp     rax, 10h
0x1400449eb  jz      loc_140044963
0x1400449f1  xor     al, al
0x1400449f3  jmp     loc_140044BD6
0x1400449f8  lea     rdi, WPP_RECORDER_INITIALIZED
0x1400449ff  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x140044a06  jz      short loc_140044A2F
0x140044a08  mov     rcx, cs:WPP_GLOBAL_Control
0x140044a0f  lea     rax, [rbx+34h]
0x140044a13  mov     [rsp+60h+var_30], rax
0x140044a18  mov     r9d, 4Fh ; 'O'
0x140044a1e  mov     rax, [rbx]
0x140044a21  mov     [rsp+60h+var_38], rax
0x140044a26  mov     rcx, [rcx+40h]
0x140044a2a  call    WPP_RECORDER_SF_i_IPV6_
0x140044a2f  mov     eax, [rbp+var_20]
0x140044a32  lea     rcx, [rax+rax*2]
0x140044a36  or      [r14+rcx*8], r15d
0x140044a3a  jmp     loc_140044BD3
0x140044a3f  lea     r9, [rbp+var_20]; unsigned int *
0x140044a43  mov     r8, rbx; struct _MIB_IPFORWARD_ROW2 *
0x140044a46  mov     edx, r12d; unsigned int
0x140044a49  mov     rcx, r13; struct _MBB_IPADDRESS_ENTRY *
0x140044a4c  call    ?MbbIpFindRouteInTable@@YAHPEAU_MBB_IPADDRESS_ENTRY@@KPEAU_MIB_IPFORWARD_ROW2@@PEAK@Z; MbbIpFindRouteInTable(_MBB_IPADDRESS_ENTRY *,ulong,_MIB_IPFORWARD_ROW2 *,ulong *)
0x140044a51  test    eax, eax
0x140044a53  jz      loc_140044B0A
0x140044a59  mov     edx, [rbp+arg_28]; unsigned int
0x140044a5c  lea     r9, [rbp+var_20]; unsigned int *
0x140044a60  mov     r8, rbx; struct _MIB_IPFORWARD_ROW2 *
0x140044a63  mov     rcx, r15; struct _MBB_IPADDRESS_ENTRY *
0x140044a66  call    ?MbbIpFindRouteInTable@@YAHPEAU_MBB_IPADDRESS_ENTRY@@KPEAU_MIB_IPFORWARD_ROW2@@PEAK@Z; MbbIpFindRouteInTable(_MBB_IPADDRESS_ENTRY *,ulong,_MIB_IPFORWARD_ROW2 *,ulong *)
0x140044a6b  test    eax, eax
0x140044a6d  jz      loc_140044B0A
0x140044a73  cmp     [rbx+64h], esi
0x140044a76  jnz     loc_140044BD3
0x140044a7c  movzx   eax, word ptr [rbx+2Ch]
0x140044a80  mov     r15d, 2
0x140044a86  cmp     r15w, ax
0x140044a8a  jnz     short loc_140044AC3
0x140044a8c  lea     rdi, WPP_RECORDER_INITIALIZED
0x140044a93  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x140044a9a  jz      short loc_140044B02
0x140044a9c  mov     rcx, cs:WPP_GLOBAL_Control
0x140044aa3  lea     rax, [rbx+30h]
0x140044aa7  mov     [rsp+60h+var_30], rax
0x140044aac  lea     r9d, [r15+51h]
0x140044ab0  mov     rax, [rbx]
0x140044ab3  mov     [rsp+60h+var_38], rax
0x140044ab8  mov     rcx, [rcx+40h]
0x140044abc  call    WPP_RECORDER_SF_i_IPV4_
0x140044ac1  jmp     short loc_140044B02
0x140044ac3  mov     ecx, 17h
0x140044ac8  cmp     cx, ax
0x140044acb  jnz     short loc_140044B02
0x140044acd  lea     rdi, WPP_RECORDER_INITIALIZED
0x140044ad4  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x140044adb  jz      short loc_140044B02
0x140044add  lea     r9d, [rcx+3Dh]
0x140044ae1  mov     rcx, cs:WPP_GLOBAL_Control
0x140044ae8  lea     rax, [rbx+34h]
0x140044aec  mov     [rsp+60h+var_30], rax
0x140044af1  mov     rax, [rbx]
0x140044af4  mov     rcx, [rcx+40h]
0x140044af8  mov     [rsp+60h+var_38], rax
0x140044afd  call    WPP_RECORDER_SF_i_IPV6_
0x140044b02  mov     sil, 1
0x140044b05  jmp     loc_140044BD3
0x140044b0a  movzx   eax, word ptr [rbx+2Ch]
0x140044b0e  lea     rdi, WPP_RECORDER_INITIALIZED
0x140044b15  mov     r15d, 2
0x140044b1b  cmp     r15w, ax
0x140044b1f  jnz     short loc_140044B51
0x140044b21  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x140044b28  jz      short loc_140044B89
0x140044b2a  mov     rcx, cs:WPP_GLOBAL_Control
0x140044b31  lea     rax, [rbx+30h]
0x140044b35  mov     [rsp+60h+var_30], rax
0x140044b3a  lea     r9d, [r15+4Eh]
0x140044b3e  mov     rax, [rbx]
0x140044b41  mov     [rsp+60h+var_38], rax
0x140044b46  mov     rcx, [rcx+40h]
0x140044b4a  call    WPP_RECORDER_SF_i_IPV4_
0x140044b4f  jmp     short loc_140044B89
0x140044b51  mov     ecx, 17h
0x140044b56  cmp     cx, ax
0x140044b59  jnz     short loc_140044B89
0x140044b5b  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x140044b62  jz      short loc_140044B89
0x140044b64  lea     r9d, [rcx+3Ah]
0x140044b68  mov     rcx, cs:WPP_GLOBAL_Control
0x140044b6f  lea     rax, [rbx+34h]
0x140044b73  mov     [rsp+60h+var_30], rax
0x140044b78  mov     rax, [rbx]
0x140044b7b  mov     rcx, [rcx+40h]
0x140044b7f  mov     [rsp+60h+var_38], rax
0x140044b84  call    WPP_RECORDER_SF_i_IPV6_
0x140044b89  mov     rcx, rbx; Row
0x140044b8c  call    cs:__imp_DeleteIpForwardEntry2
0x140044b93  nop     dword ptr [rax+rax+00h]
0x140044b98  test    eax, eax
0x140044b9a  jz      short loc_140044BD3
0x140044b9c  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x140044ba3  jz      short loc_140044BD3
0x140044ba5  mov     rcx, [rbx]
0x140044ba8  mov     r9d, 52h ; 'R'
0x140044bae  mov     dword ptr [rsp+60h+var_30], eax
0x140044bb2  lea     rax, WPP_f53708f2277a3aabca584f524242a299_Traceguids
0x140044bb9  mov     [rsp+60h+var_38], rcx
0x140044bbe  mov     rcx, cs:WPP_GLOBAL_Control
0x140044bc5  mov     [rsp+60h+var_40], rax
0x140044bca  mov     rcx, [rcx+40h]
0x140044bce  call    WPP_RECORDER_SF_id
0x140044bd3  mov     al, sil
0x140044bd6  mov     rcx, [rbp+var_8]
0x140044bda  xor     rcx, rsp; StackCookie
0x140044bdd  call    __security_check_cookie
0x140044be2  mov     rbx, [rsp+60h+arg_8]
0x140044bea  add     rsp, 60h
0x140044bee  pop     r15
0x140044bf0  pop     r14
0x140044bf2  pop     r13
0x140044bf4  pop     r12
0x140044bf6  pop     rdi
0x140044bf7  pop     rsi
0x140044bf8  pop     rbp
0x140044bf9  retn
```
