# FindArchivedMessageAfterAccessCheck

- ea: `0x1400135d0`
- end: `0x1400138c2`
- name: `FindArchivedMessageAfterAccessCheck`
- size: `754`
- prototype: `__int64 __fastcall(unsigned int, unsigned __int64, unsigned int, int, wchar_t *Str)`
- caller_count: `5`
- callee_count: `10`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1400112c8`
- `0x140011650`
- `0x14001b190`
- `0x14001d790`
- `0x140021e70`

## callees

- `0x140004c78`
- `0x140004ca8`
- `0x140006d38`
- `0x14000c5a4`
- `0x14001034c`
- `0x1400135d0`
- `0x1400239ac`
- `0x140048284`
- `0x140051dec`
- `0x14006998c`

## import_xrefs

- `ADVAPI32!EqualSid` at `0x140013849`
- `ADVAPI32!EqualSid` at `0x140013849`
- `KERNEL32!GetLastError` at `0x1400136c3`
- `KERNEL32!GetLastError` at `0x1400136c3`
- `KERNEL32!LocalFree` at `0x1400138a2`
- `KERNEL32!LocalFree` at `0x1400138a2`
- `msvcrt!wcsrchr` at `0x14001378b`
- `msvcrt!wcsrchr` at `0x14001378b`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall FindArchivedMessageAfterAccessCheck(
        unsigned int a1,
        unsigned __int64 a2,
        unsigned int a3,
        int a4,
        wchar_t *Str)
{
  PSID v5; // rdi
  BOOL v8; // r13d
  int v10; // ebp
  CMapDeviceId *v11; // rcx
  void *ClientUserSID; // rax
  CFaxArchiving *v14; // rcx
  void *v15; // rsi
  DWORD LastError; // ebx
  void *v17; // r9
  wchar_t *v18; // r12
  __int64 v19; // rdx
  __int64 v20; // r8
  wchar_t *v21; // rax
  CFaxArchiving *v22; // rcx
  const unsigned __int16 *v23; // rdx
  CMapDeviceId *v24; // rcx
  __int64 v25; // rdx
  unsigned int v26; // [rsp+28h] [rbp-50h]
  PSID pSid2; // [rsp+88h] [rbp+10h] BYREF

  v5 = 0;
  pSid2 = 0;
  v8 = a1 == 1;
  v10 = a4 != 0 ? 128 : 256;
  v11 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 457, &WPP_bf13a1f9149c312b3fa8c47129651a46_Traceguids);
    v11 = WPP_GLOBAL_Control;
  }
  if ( !a2 )
  {
    if ( v11 != (CMapDeviceId *)&WPP_GLOBAL_Control && (*((_BYTE *)v11 + 28) & 4) != 0 && *((_BYTE *)v11 + 25) >= 2u )
      WPP_SF_i(*((_QWORD *)v11 + 2), 458, &WPP_bf13a1f9149c312b3fa8c47129651a46_Traceguids, 0);
    return 87;
  }
  if ( a1 > 1 )
  {
    if ( v11 != (CMapDeviceId *)&WPP_GLOBAL_Control && (*((_BYTE *)v11 + 28) & 4) != 0 && *((_BYTE *)v11 + 25) >= 2u )
      WPP_SF_d(*((_QWORD *)v11 + 2), 459, &WPP_bf13a1f9149c312b3fa8c47129651a46_Traceguids, a1);
    return 87;
  }
  ClientUserSID = GetClientUserSID();
  v15 = ClientUserSID;
  if ( !ClientUserSID )
  {
    LastError = GetLastError();
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 460, &WPP_bf13a1f9149c312b3fa8c47129651a46_Traceguids, LastError);
    }
    goto LABEL_53;
  }
  v17 = 0;
  if ( a1 == 1 && (v10 & a3) == 0 )
    v17 = ClientUserSID;
  v18 = Str;
  LastError = CFaxArchiving::SearchMessage(v14, a2, v8, v17, Str, v26);
  if ( LastError )
  {
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_il(*((_QWORD *)WPP_GLOBAL_Control + 2), v19, v20, a2, LastError);
    }
    if ( LastError != 2 )
      goto LABEL_53;
    goto LABEL_52;
  }
  v21 = wcsrchr(v18, 0x5Cu);
  v23 = v21 + 1;
  if ( !v21 )
    v23 = 0;
  LastError = CFaxArchiving::ExtractComponentsFromArchiveFileName(v22, v23, 0, &pSid2);
  if ( LastError )
  {
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 462, &WPP_bf13a1f9149c312b3fa8c47129651a46_Traceguids, LastError);
    }
    v5 = pSid2;
    goto LABEL_53;
  }
  v5 = pSid2;
  if ( pSid2 )
  {
    if ( (v10 & a3) != 0 || EqualSid(v15, pSid2) )
      goto LABEL_53;
    v24 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_52;
    }
    v25 = 464;
    goto LABEL_51;
  }
  if ( !(unsigned int)CanAccessUnAssignedFaxes(a3, 1) )
  {
    v24 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_52;
    }
    v25 = 463;
LABEL_51:
    WPP_SF_(*((_QWORD *)v24 + 2), v25, &WPP_bf13a1f9149c312b3fa8c47129651a46_Traceguids);
LABEL_52:
    LastError = 7009;
  }
LABEL_53:
  pMemFree(v15);
  if ( v5 )
    LocalFree(v5);
  return LastError;
}

```

## disassembly

```asm
0x1400135d0  mov     rax, rsp
0x1400135d3  push    rbx
0x1400135d4  push    rbp
0x1400135d5  push    rsi
0x1400135d6  push    rdi
0x1400135d7  push    r12
0x1400135d9  push    r13
0x1400135db  push    r14
0x1400135dd  push    r15
0x1400135df  sub     rsp, 38h
0x1400135e3  xor     edi, edi
0x1400135e5  xor     r13d, r13d
0x1400135e8  cmp     ecx, 1
0x1400135eb  mov     [rax+10h], rdi
0x1400135ef  mov     r15d, r8d
0x1400135f2  mov     r14, rdx
0x1400135f5  setz    r13b
0x1400135f9  mov     ebx, ecx
0x1400135fb  neg     r9d
0x1400135fe  sbb     ebp, ebp
0x140013600  and     ebp, 0FFFFFF80h
0x140013603  add     ebp, 100h
0x140013609  mov     rcx, cs:WPP_GLOBAL_Control
0x140013610  lea     rax, WPP_GLOBAL_Control
0x140013617  mov     r12b, 4
0x14001361a  cmp     rcx, rax
0x14001361d  jz      short loc_14001364E
0x14001361f  test    [rcx+1Ch], r12b
0x140013623  jz      short loc_14001364E
0x140013625  cmp     byte ptr [rcx+19h], 5
0x140013629  jb      short loc_14001364E
0x14001362b  mov     rcx, [rcx+10h]
0x14001362f  lea     r8, WPP_bf13a1f9149c312b3fa8c47129651a46_Traceguids
0x140013636  mov     edx, 1C9h
0x14001363b  call    WPP_SF_
0x140013640  mov     rcx, cs:WPP_GLOBAL_Control
0x140013647  lea     rax, WPP_GLOBAL_Control
0x14001364e  test    r14, r14
0x140013651  jnz     short loc_14001367E
0x140013653  cmp     rcx, rax
0x140013656  jz      short loc_1400136AC
0x140013658  test    [rcx+1Ch], r12b
0x14001365c  jz      short loc_1400136AC
0x14001365e  cmp     byte ptr [rcx+19h], 2
0x140013662  jb      short loc_1400136AC
0x140013664  mov     rcx, [rcx+10h]
0x140013668  lea     r8, WPP_bf13a1f9149c312b3fa8c47129651a46_Traceguids
0x14001366f  mov     edx, 1CAh
0x140013674  xor     r9d, r9d
0x140013677  call    WPP_SF_i
0x14001367c  jmp     short loc_1400136AC
0x14001367e  cmp     ebx, 1
0x140013681  jbe     short loc_1400136B6
0x140013683  cmp     rcx, rax
0x140013686  jz      short loc_1400136AC
0x140013688  test    [rcx+1Ch], r12b
0x14001368c  jz      short loc_1400136AC
0x14001368e  cmp     byte ptr [rcx+19h], 2
0x140013692  jb      short loc_1400136AC
0x140013694  mov     rcx, [rcx+10h]
0x140013698  lea     r8, WPP_bf13a1f9149c312b3fa8c47129651a46_Traceguids
0x14001369f  mov     edx, 1CBh
0x1400136a4  mov     r9d, ebx
0x1400136a7  call    WPP_SF_d
0x1400136ac  mov     eax, 57h ; 'W'
0x1400136b1  jmp     loc_1400138B0
0x1400136b6  call    ?GetClientUserSID@@YAPEAXXZ; GetClientUserSID(void)
0x1400136bb  mov     rsi, rax
0x1400136be  test    rax, rax
0x1400136c1  jnz     short loc_140013719
0x1400136c3  call    cs:__imp_GetLastError
0x1400136ca  nop     dword ptr [rax+rax+00h]
0x1400136cf  mov     ebx, eax
0x1400136d1  mov     rcx, cs:WPP_GLOBAL_Control
0x1400136d8  lea     rax, WPP_GLOBAL_Control
0x1400136df  cmp     rcx, rax
0x1400136e2  jz      loc_140013892
0x1400136e8  test    [rcx+1Ch], r12b
0x1400136ec  jz      loc_140013892
0x1400136f2  cmp     byte ptr [rcx+19h], 2
0x1400136f6  jb      loc_140013892
0x1400136fc  mov     rcx, [rcx+10h]
0x140013700  lea     r8, WPP_bf13a1f9149c312b3fa8c47129651a46_Traceguids
0x140013707  mov     edx, 1CCh
0x14001370c  mov     r9d, ebx
0x14001370f  call    WPP_SF_d
0x140013714  jmp     loc_140013892
0x140013719  xor     r9d, r9d
0x14001371c  cmp     ebx, 1
0x14001371f  jnz     short loc_140013728
0x140013721  test    r15d, ebp
0x140013724  cmovz   r9, rsi; void *
0x140013728  mov     r12, [rsp+78h+Str]
0x140013730  mov     r8d, r13d; int
0x140013733  mov     rdx, r14; unsigned __int64
0x140013736  mov     [rsp+78h+var_58], r12; unsigned __int16 *
0x14001373b  call    ?SearchMessage@CFaxArchiving@@QEAAK_KHPEAXPEAGK@Z; CFaxArchiving::SearchMessage(unsigned __int64,int,void *,ushort *,ulong)
0x140013740  mov     ebx, eax
0x140013742  test    eax, eax
0x140013744  jz      short loc_140013783
0x140013746  mov     rcx, cs:WPP_GLOBAL_Control
0x14001374d  lea     rax, WPP_GLOBAL_Control
0x140013754  cmp     rcx, rax
0x140013757  jz      short loc_140013775
0x140013759  test    byte ptr [rcx+1Ch], 4
0x14001375d  jz      short loc_140013775
0x14001375f  cmp     byte ptr [rcx+19h], 2
0x140013763  jb      short loc_140013775
0x140013765  mov     rcx, [rcx+10h]
0x140013769  mov     r9, r14
0x14001376c  mov     dword ptr [rsp+78h+var_58], ebx
0x140013770  call    WPP_SF_il
0x140013775  cmp     ebx, 2
0x140013778  jnz     loc_140013892
0x14001377e  jmp     loc_14001388D
0x140013783  mov     edx, 5Ch ; '\'; Ch
0x140013788  mov     rcx, r12; Str
0x14001378b  call    cs:__imp_wcsrchr
0x140013792  nop     dword ptr [rax+rax+00h]
0x140013797  test    rax, rax
0x14001379a  lea     r9, [rsp+78h+pSid2]; void **
0x1400137a2  lea     rdx, [rax+2]
0x1400137a6  cmovz   rdx, rax; unsigned __int16 *
0x1400137aa  xor     r8d, r8d; unsigned __int64 *
0x1400137ad  call    ?ExtractComponentsFromArchiveFileName@CFaxArchiving@@QEAAKPEBGPEA_KPEAPEAX@Z; CFaxArchiving::ExtractComponentsFromArchiveFileName(ushort const *,unsigned __int64 *,void * *)
0x1400137b2  mov     ebx, eax
0x1400137b4  test    eax, eax
0x1400137b6  jz      short loc_1400137FC
0x1400137b8  mov     rcx, cs:WPP_GLOBAL_Control
0x1400137bf  lea     rax, WPP_GLOBAL_Control
0x1400137c6  cmp     rcx, rax
0x1400137c9  jz      short loc_1400137EF
0x1400137cb  test    byte ptr [rcx+1Ch], 4
0x1400137cf  jz      short loc_1400137EF
0x1400137d1  cmp     byte ptr [rcx+19h], 2
0x1400137d5  jb      short loc_1400137EF
0x1400137d7  mov     rcx, [rcx+10h]
0x1400137db  lea     r8, WPP_bf13a1f9149c312b3fa8c47129651a46_Traceguids
0x1400137e2  mov     edx, 1CEh
0x1400137e7  mov     r9d, ebx
0x1400137ea  call    WPP_SF_d
0x1400137ef  mov     rdi, [rsp+78h+pSid2]
0x1400137f7  jmp     loc_140013892
0x1400137fc  mov     rdi, [rsp+78h+pSid2]
0x140013804  test    rdi, rdi
0x140013807  jnz     short loc_14001383E
0x140013809  lea     edx, [rdi+1]; int
0x14001380c  mov     ecx, r15d; unsigned int
0x14001380f  call    ?CanAccessUnAssignedFaxes@@YAHKH@Z; CanAccessUnAssignedFaxes(ulong,int)
0x140013814  test    eax, eax
0x140013816  jnz     short loc_140013892
0x140013818  mov     rcx, cs:WPP_GLOBAL_Control
0x14001381f  lea     rax, WPP_GLOBAL_Control
0x140013826  cmp     rcx, rax
0x140013829  jz      short loc_14001388D
0x14001382b  test    byte ptr [rcx+1Ch], 4
0x14001382f  jz      short loc_14001388D
0x140013831  cmp     byte ptr [rcx+19h], 2
0x140013835  jb      short loc_14001388D
0x140013837  mov     edx, 1CFh
0x14001383c  jmp     short loc_14001387D
0x14001383e  test    r15d, ebp
0x140013841  jnz     short loc_140013892
0x140013843  mov     rdx, rdi; pSid2
0x140013846  mov     rcx, rsi; pSid1
0x140013849  call    cs:__imp_EqualSid
0x140013850  nop     dword ptr [rax+rax+00h]
0x140013855  test    eax, eax
0x140013857  jnz     short loc_140013892
0x140013859  mov     rcx, cs:WPP_GLOBAL_Control
0x140013860  lea     rax, WPP_GLOBAL_Control
0x140013867  cmp     rcx, rax
0x14001386a  jz      short loc_14001388D
0x14001386c  test    byte ptr [rcx+1Ch], 4
0x140013870  jz      short loc_14001388D
0x140013872  cmp     byte ptr [rcx+19h], 2
0x140013876  jb      short loc_14001388D
0x140013878  mov     edx, 1D0h
0x14001387d  mov     rcx, [rcx+10h]
0x140013881  lea     r8, WPP_bf13a1f9149c312b3fa8c47129651a46_Traceguids
0x140013888  call    WPP_SF_
0x14001388d  mov     ebx, 1B61h
0x140013892  mov     rcx, rsi; lpMem
0x140013895  call    pMemFree
0x14001389a  test    rdi, rdi
0x14001389d  jz      short loc_1400138AE
0x14001389f  mov     rcx, rdi; hMem
0x1400138a2  call    cs:__imp_LocalFree
0x1400138a9  nop     dword ptr [rax+rax+00h]
0x1400138ae  mov     eax, ebx
0x1400138b0  add     rsp, 38h
0x1400138b4  pop     r15
0x1400138b6  pop     r14
0x1400138b8  pop     r13
0x1400138ba  pop     r12
0x1400138bc  pop     rdi
0x1400138bd  pop     rsi
0x1400138be  pop     rbp
0x1400138bf  pop     rbx
0x1400138c0  retn
```
