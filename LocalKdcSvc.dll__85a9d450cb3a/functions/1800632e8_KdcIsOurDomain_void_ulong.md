# KdcIsOurDomain(void *,ulong *)

- ea: `0x1800632e8`
- end: `0x1800633b5`
- name: `?KdcIsOurDomain@@YAEPEAXPEAK@Z`
- size: `205`
- prototype: `unsigned __int8 __fastcall(void *, unsigned int *)`
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180054598`
- `0x18005c560`

## callees

- `0x1800101ec`
- `0x18002057c`
- `0x1800632e8`
- `0x180067400`

## import_xrefs

- `ntdll!RtlEqualSid` at `0x180063304`
- `ntdll!RtlEqualSid` at `0x180063304`

## pseudocode

```c
char __fastcall KdcIsOurDomain(_BYTE *a1, unsigned int *a2)
{
  char v4; // di
  __int64 v5; // rdx
  __int64 v6; // r8
  CSecurityData *v7; // rcx
  __int64 v8; // r9

  --a1[1];
  v4 = 0;
  if ( RtlEqualSid(a1, GlobalDomainSid) )
  {
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control )
    {
      if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000) != 0 )
      {
        WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 130, WPP_b168486f65343579948eb0cc9cf7c178_Traceguids, a1);
        v7 = WPP_GLOBAL_Control;
      }
      if ( v7 != (CSecurityData *)&WPP_GLOBAL_Control && (*((_DWORD *)v7 + 7) & 0x8000) != 0 )
        WPP_SF_qd(*((_QWORD *)v7 + 2), v5, v6, &a1[4 * (unsigned __int8)a1[1] + 8], (unsigned __int8)a1[1]);
    }
    v8 = *(unsigned int *)&a1[4 * (unsigned __int8)a1[1] + 8];
    *a2 = v8;
    if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000) != 0 )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 132, WPP_b168486f65343579948eb0cc9cf7c178_Traceguids, v8);
    }
    v4 = 1;
  }
  ++a1[1];
  return v4;
}

```

## disassembly

```asm
0x1800632e8  push    rbx
0x1800632ea  push    rbp
0x1800632eb  push    rsi
0x1800632ec  push    rdi
0x1800632ed  sub     rsp, 38h
0x1800632f1  dec     byte ptr [rcx+1]
0x1800632f4  mov     rsi, rdx
0x1800632f7  mov     rdx, cs:?GlobalDomainSid@@3PEAXEA; Sid2
0x1800632fe  mov     rbx, rcx
0x180063301  xor     dil, dil
0x180063304  call    cs:__imp_RtlEqualSid
0x18006330a  test    al, al
0x18006330c  jz      loc_1800633A6
0x180063312  mov     rcx, cs:WPP_GLOBAL_Control
0x180063319  lea     rbp, WPP_GLOBAL_Control
0x180063320  mov     edi, 8000h
0x180063325  cmp     rcx, rbp
0x180063328  jz      short loc_180063371
0x18006332a  test    [rcx+1Ch], edi
0x18006332d  jz      short loc_18006334E
0x18006332f  mov     rcx, [rcx+10h]
0x180063333  lea     r8, WPP_b168486f65343579948eb0cc9cf7c178_Traceguids
0x18006333a  mov     edx, 82h
0x18006333f  mov     r9, rbx
0x180063342  call    WPP_SF_q
0x180063347  mov     rcx, cs:WPP_GLOBAL_Control
0x18006334e  cmp     rcx, rbp
0x180063351  jz      short loc_180063371
0x180063353  test    [rcx+1Ch], edi
0x180063356  jz      short loc_180063371
0x180063358  movzx   eax, byte ptr [rbx+1]
0x18006335c  lea     r9, [rbx+8]
0x180063360  mov     rcx, [rcx+10h]
0x180063364  mov     [rsp+58h+var_38], eax
0x180063368  lea     r9, [r9+rax*4]
0x18006336c  call    WPP_SF_qd
0x180063371  movzx   eax, byte ptr [rbx+1]
0x180063375  mov     r9d, [rbx+rax*4+8]
0x18006337a  mov     [rsi], r9d
0x18006337d  mov     rcx, cs:WPP_GLOBAL_Control
0x180063384  cmp     rcx, rbp
0x180063387  jz      short loc_1800633A3
0x180063389  test    [rcx+1Ch], edi
0x18006338c  jz      short loc_1800633A3
0x18006338e  mov     rcx, [rcx+10h]
0x180063392  lea     r8, WPP_b168486f65343579948eb0cc9cf7c178_Traceguids
0x180063399  mov     edx, 84h
0x18006339e  call    WPP_SF_d
0x1800633a3  mov     dil, 1
0x1800633a6  inc     byte ptr [rbx+1]
0x1800633a9  mov     al, dil
0x1800633ac  add     rsp, 38h
0x1800633b0  pop     rdi
0x1800633b1  pop     rsi
0x1800633b2  pop     rbp
0x1800633b3  pop     rbx
0x1800633b4  retn
```
