# Broker::BILayer::QueryUserContext(unsigned __int64,Broker::ApplicationIdentity *,ulong *)

- ea: `0x18000ccbc`
- end: `0x18000cda6`
- name: `?QueryUserContext@BILayer@Broker@@YA_N_KPEAUApplicationIdentity@2@PEAK@Z`
- size: `234`
- prototype: `bool __fastcall(Broker::BILayer *__hidden this, unsigned __int64, struct Broker::ApplicationIdentity *, unsigned int *)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000c4c0`

## callees

- `0x180006cec`
- `0x180009e94`
- `0x18000ccbc`
- `0x18000fe88`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18000cd2e`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18000cd2e`
- `api-ms-win-core-bicltapi-l1-1-6!BiQueryUserContext` at `0x18000ccdc`
- `api-ms-win-core-bicltapi-l1-1-6!BiQueryUserContext` at `0x18000ccdc`
- `api-ms-win-core-bicltapi-l1-1-6!BiFreeMemory` at `0x18000cd1c`
- `api-ms-win-core-bicltapi-l1-1-6!BiFreeMemory` at `0x18000cd95`
- `api-ms-win-core-bicltapi-l1-1-6!BiFreeMemory` at `0x18000cd1c`
- `api-ms-win-core-bicltapi-l1-1-6!BiFreeMemory` at `0x18000cd95`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
char __fastcall Broker::BILayer::QueryUserContext(
        Broker::BILayer *this,
        __int64 *a2,
        struct Broker::ApplicationIdentity *a3,
        unsigned int *a4)
{
  int v6; // eax
  char *v8; // rdi
  __int64 LengthSid; // rbp
  __int64 v10; // rdx
  char v11[4]; // [rsp+20h] [rbp-38h]
  PSID pSid; // [rsp+78h] [rbp+20h] BYREF

  pSid = 0;
  v6 = BiQueryUserContext(this, a3, &pSid, a4);
  if ( v6 >= 0 )
  {
    v8 = (char *)pSid;
    LengthSid = GetLengthSid(pSid);
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    {
      *(_DWORD *)v11 = *(_DWORD *)a3;
      WPP_SF__sid_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        0x24u,
        &WPP_6d22d7a2e1813c043b7d2163e38154fa_Traceguids,
        v8,
        *(_DWORD *)v11);
    }
    v10 = *a2;
    if ( *a2 == a2[1] )
      v10 = a2[1];
    else
      a2[1] = v10;
    std::vector<unsigned char>::_Insert_counted_range<unsigned char *>(a2, v10, v8, LengthSid);
    if ( pSid )
      BiFreeMemory();
    return 1;
  }
  else
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        35,
        &WPP_6d22d7a2e1813c043b7d2163e38154fa_Traceguids,
        (unsigned int)v6);
    if ( pSid )
      BiFreeMemory();
    return 0;
  }
}

```

## disassembly

```asm
0x18000ccbc  push    rbx
0x18000ccbe  push    rbp
0x18000ccbf  push    rsi
0x18000ccc0  push    rdi
0x18000ccc1  sub     rsp, 38h
0x18000ccc5  mov     rsi, r8
0x18000ccc8  mov     rbx, rdx
0x18000cccb  mov     [rsp+58h+pSid], 0
0x18000ccd4  lea     r8, [rsp+58h+pSid]
0x18000ccd9  mov     rdx, rsi
0x18000ccdc  call    cs:__imp_BiQueryUserContext
0x18000cce2  test    eax, eax
0x18000cce4  jns     short loc_18000CD26
0x18000cce6  mov     rcx, cs:WPP_GLOBAL_Control
0x18000cced  test    byte ptr [rcx+1Ch], 1
0x18000ccf1  jz      short loc_18000CD12
0x18000ccf3  cmp     byte ptr [rcx+19h], 2
0x18000ccf7  jb      short loc_18000CD12
0x18000ccf9  mov     edx, 23h ; '#'
0x18000ccfe  mov     r9d, eax
0x18000cd01  lea     r8, WPP_6d22d7a2e1813c043b7d2163e38154fa_Traceguids
0x18000cd08  mov     rcx, [rcx+10h]
0x18000cd0c  call    WPP_SF_d
0x18000cd11  nop
0x18000cd12  mov     rcx, [rsp+58h+pSid]
0x18000cd17  test    rcx, rcx
0x18000cd1a  jz      short loc_18000CD22
0x18000cd1c  call    cs:__imp_BiFreeMemory
0x18000cd22  xor     al, al
0x18000cd24  jmp     short loc_18000CD9D
0x18000cd26  mov     rdi, [rsp+58h+pSid]
0x18000cd2b  mov     rcx, rdi; pSid
0x18000cd2e  call    cs:__imp_GetLengthSid
0x18000cd34  mov     ebp, eax
0x18000cd36  mov     rcx, cs:WPP_GLOBAL_Control
0x18000cd3d  test    byte ptr [rcx+1Ch], 1
0x18000cd41  jz      short loc_18000CD69
0x18000cd43  cmp     byte ptr [rcx+19h], 5
0x18000cd47  jb      short loc_18000CD69
0x18000cd49  mov     edx, 24h ; '$'
0x18000cd4e  mov     r8d, [rsi]
0x18000cd51  mov     dword ptr [rsp+58h+var_38], r8d; char
0x18000cd56  mov     r9, rdi
0x18000cd59  lea     r8, WPP_6d22d7a2e1813c043b7d2163e38154fa_Traceguids
0x18000cd60  mov     rcx, [rcx+10h]; LoggerHandle
0x18000cd64  call    WPP_SF__sid_d
0x18000cd69  mov     rdx, [rbx]
0x18000cd6c  cmp     rdx, [rbx+8]
0x18000cd70  jz      short loc_18000CD78
0x18000cd72  mov     [rbx+8], rdx
0x18000cd76  jmp     short loc_18000CD7C
0x18000cd78  mov     rdx, [rbx+8]
0x18000cd7c  mov     r9, rbp
0x18000cd7f  mov     r8, rdi
0x18000cd82  mov     rcx, rbx
0x18000cd85  call    ??$_Insert_counted_range@PEAE@?$vector@EV?$allocator@E@std@@@std@@AEAAXV?$_Vector_const_iterator@V?$_Vector_val@U?$_Simple_types@E@std@@@std@@@1@PEAE_K@Z; std::vector<uchar>::_Insert_counted_range<uchar *>(std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<uchar>>>,uchar *,unsigned __int64)
0x18000cd8a  nop
0x18000cd8b  mov     rcx, [rsp+58h+pSid]
0x18000cd90  test    rcx, rcx
0x18000cd93  jz      short loc_18000CD9B
0x18000cd95  call    cs:__imp_BiFreeMemory
0x18000cd9b  mov     al, 1
0x18000cd9d  add     rsp, 38h
0x18000cda1  pop     rdi
0x18000cda2  pop     rsi
0x18000cda3  pop     rbp
0x18000cda4  pop     rbx
0x18000cda5  retn
```
