# NDXGI::CDevice::SubmitCommandCB(void *,_D3DDDICB_SUBMITCOMMAND const *)

- ea: `0x180053830`
- end: `0x180053a9e`
- name: `?SubmitCommandCB@CDevice@NDXGI@@KAJPEAXPEBU_D3DDDICB_SUBMITCOMMAND@@@Z`
- size: `622`
- prototype: `__int64 __fastcall(NDXGI::CDevice *this, const struct _D3DDDICB_SUBMITCOMMAND *)`
- caller_count: `0`
- callee_count: `9`
- tags: `broker_com_uri`

## callees

- `0x180007df0`
- `0x180053830`
- `0x180053aa4`
- `0x18007efa0`
- `0x18007f054`
- `0x1800a6754`
- `0x1800bb480`
- `0x1800bc094`
- `0x18011ace0`

## import_xrefs

- `ext-ms-win-dx-d3dkmt-dxcore-l1-1-0!__imp_D3DKMTSubmitCommand` at `0x180053a3a`

## string_xrefs

- `0x1800538cd`: `D3DDDICB_SUBMITCOMMAND::BroadcastContext array must contain contexts that are all associated with the same command queue.\n`
- `0x1800538d6`: `D3DDDICB_SUBMITCOMMAND::BroadcastContext array may not contain contexts that belong to a scheduling group.\n`
- `0x18005388f`: `D3DDDICB_SUBMITCOMMAND::BroadcastContextCount is too large.\n`
- `0x1800538ea`: `D3DDDICB_SUBMITCOMMAND::NumPrimaries is too large. Only half the available array may be used by driver.\n`

## pseudocode

```c
__int64 __fastcall NDXGI::CDevice::SubmitCommandCB(
        __int64 this,
        const struct _D3DDDICB_SUBMITCOMMAND *a2,
        __int64 a3,
        __int64 a4)
{
  int *v5; // r15
  __int64 result; // rax
  const char *v7; // r8
  struct CCastableCommandQueue *v8; // r14
  __int64 v9; // rdx
  unsigned int v10; // esi
  __int64 i; // rdx
  __int64 *v12; // rax
  __int64 j; // r8
  unsigned int v14; // edi
  int v15; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v16; // [rsp+40h] [rbp-C0h] BYREF
  int v17; // [rsp+48h] [rbp-B8h]
  int v18; // [rsp+4Ch] [rbp-B4h]
  __int64 v19; // [rsp+50h] [rbp-B0h]
  unsigned int v20; // [rsp+58h] [rbp-A8h]
  _DWORD v21[65]; // [rsp+5Ch] [rbp-A4h]
  __int64 v22; // [rsp+160h] [rbp+60h]
  int v23; // [rsp+168h] [rbp+68h]
  unsigned int v24; // [rsp+16Ch] [rbp+6Ch]
  _DWORD v25[16]; // [rsp+170h] [rbp+70h]
  int v26; // [rsp+1B0h] [rbp+B0h]
  int *v27; // [rsp+1B8h] [rbp+B8h]

  v5 = (int *)this;
  if ( *((_DWORD *)a2 + 3) >= 2u )
  {
    CJournal::RecordJournal(this, -2147024809, (__int64)"Reserved flags given to RenderCb", a4, 0);
    return 2147942487LL;
  }
  if ( *((_DWORD *)a2 + 4) > 0x40u )
  {
    v7 = "D3DDDICB_SUBMITCOMMAND::BroadcastContextCount is too large.\n";
LABEL_6:
    CJournal::ReportDriverError((CJournal *)this, -2147024809, v7);
    return 2147942487LL;
  }
  v8 = 0;
  for ( this = 0; (unsigned int)this < *((_DWORD *)a2 + 4); this = (unsigned int)(this + 1) )
  {
    v9 = *((_QWORD *)a2 + (unsigned int)this + 3);
    if ( (_DWORD)this && *(struct CCastableCommandQueue **)(v9 + 8) != v8 )
    {
      v7 = "D3DDDICB_SUBMITCOMMAND::BroadcastContext array must contain contexts that are all associated with the same command queue.\n";
      goto LABEL_6;
    }
    if ( *(_QWORD *)(v9 + 16) )
    {
      v7 = "D3DDDICB_SUBMITCOMMAND::BroadcastContext array may not contain contexts that belong to a scheduling group.\n";
      goto LABEL_6;
    }
    v8 = *(struct CCastableCommandQueue **)(v9 + 8);
  }
  v10 = *((_DWORD *)a2 + 137);
  if ( v10 > 8 )
  {
    v7 = "D3DDDICB_SUBMITCOMMAND::NumPrimaries is too large. Only half the available array may be used by driver.\n";
    goto LABEL_6;
  }
  if ( *((_DWORD *)a2 + 154) )
  {
    if ( (int)NDXGI::CDevice::ETWWriteSubmitCommandCB((NDXGI::CDevice *)this, a2, v8) < 0 )
      return 2147942487LL;
    v10 = *((_DWORD *)a2 + 137);
  }
  v15 = 0;
  memset_0(&v16, 0, 0x180u);
  v16 = *(_QWORD *)a2;
  v17 = *((_DWORD *)a2 + 2);
  v18 = *((_DWORD *)a2 + 3) & 1;
  v19 = 0;
  v20 = *((_DWORD *)a2 + 4);
  if ( *((_DWORD *)a2 + 154) )
  {
    if ( *((_DWORD *)a2 + 170) )
    {
      v15 = *((_DWORD *)a2 + 170);
      v27 = &v15;
      v26 = 1;
    }
    else
    {
      v27 = (int *)*((_QWORD *)a2 + 86);
      v26 = *((_DWORD *)a2 + 171);
    }
  }
  else
  {
    v27 = 0;
    v26 = 0;
  }
  v24 = v10;
  for ( i = 0; (unsigned int)i < v24; v10 = v24 )
  {
    v25[(unsigned int)i] = *((_DWORD *)a2 + (unsigned int)i + 138);
    i = (unsigned int)(i + 1);
  }
  if ( v8 )
  {
    v12 = (__int64 *)*((_QWORD *)v8 + 39);
    while ( 1 )
    {
      v12 = (__int64 *)*v12;
      if ( v12 == *((__int64 **)v8 + 39) )
        break;
      i = v10;
      v25[v10] = *((_DWORD *)v12 + 6);
      v10 = ++v24;
    }
  }
  for ( j = 0; (unsigned int)j < v20; j = (unsigned int)(j + 1) )
  {
    i = (unsigned int)j;
    v21[(unsigned int)j] = *(_DWORD *)(*((_QWORD *)a2 + (unsigned int)j + 3) + 24LL);
  }
  v22 = *((_QWORD *)a2 + 67);
  v23 = *((_DWORD *)a2 + 136);
  if ( v5[338] < 0 )
    return 0;
  v14 = CallAndLogImpl<long (*)(_D3DKMT_SUBMITCOMMAND const *),_D3DKMT_SUBMITCOMMAND *>(D3DKMTSubmitCommand, i, j, &v16);
  result = NDXGI::CDevice::NTStatusToHResult(v5, v14, 0);
  if ( (int)result < 0 )
  {
    if ( v14 == -1073741790 )
    {
      NDXGI::CDevice::RemoveDevice((NDXGI::CDevice *)v5, -2005270485);
      return 0;
    }
    if ( (_DWORD)result == -2005530512 )
      return 0;
  }
  return result;
}

```

## disassembly

```asm
0x180053830  mov     [rsp-8+arg_10], rbx
0x180053835  push    rbp
0x180053836  push    rsi
0x180053837  push    rdi
0x180053838  push    r14
0x18005383a  push    r15
0x18005383c  lea     rbp, [rsp-0D0h]
0x180053844  sub     rsp, 1D0h
0x18005384b  mov     rax, cs:__security_cookie
0x180053852  xor     rax, rsp
0x180053855  mov     [rbp+0F0h+var_30], rax
0x18005385c  mov     rdi, rdx
0x18005385f  mov     r15, rcx
0x180053862  cmp     dword ptr [rdx+0Ch], 2
0x180053866  jb      short loc_180053889
0x180053868  xor     ebx, ebx
0x18005386a  mov     [rsp+1F0h+var_1D0], ebx
0x18005386e  lea     r8, aReservedFlagsG_1; "Reserved flags given to RenderCb"
0x180053875  mov     edx, 80070057h
0x18005387a  call    ?RecordJournal@CJournal@@QEAAXIPEBD_NW4RecordJournalOptions@@@Z; CJournal::RecordJournal(uint,char const *,bool,RecordJournalOptions)
0x18005387f  mov     eax, 80070057h
0x180053884  jmp     loc_180053A78
0x180053889  cmp     dword ptr [rdx+10h], 40h ; '@'
0x18005388d  jbe     short loc_1800538A2
0x18005388f  lea     r8, aD3dddicbSubmit; "D3DDDICB_SUBMITCOMMAND::BroadcastContex"...
0x180053896  mov     edx, 80070057h; int
0x18005389b  call    ?ReportDriverError@CJournal@@QEAAXJPEBD@Z; CJournal::ReportDriverError(long,char const *)
0x1800538a0  jmp     short loc_18005387F
0x1800538a2  xor     ebx, ebx
0x1800538a4  mov     r14d, ebx
0x1800538a7  mov     ecx, ebx; this
0x1800538a9  cmp     ecx, [rdi+10h]
0x1800538ac  jnb     short loc_1800538DF
0x1800538ae  mov     eax, ecx
0x1800538b0  mov     rdx, [rdi+rax*8+18h]
0x1800538b5  test    ecx, ecx
0x1800538b7  jz      short loc_1800538BF
0x1800538b9  cmp     [rdx+8], r14
0x1800538bd  jnz     short loc_1800538CD
0x1800538bf  cmp     [rdx+10h], rbx
0x1800538c3  jnz     short loc_1800538D6
0x1800538c5  mov     r14, [rdx+8]
0x1800538c9  inc     ecx
0x1800538cb  jmp     short loc_1800538A9
0x1800538cd  lea     r8, aD3dddicbSubmit_0; "D3DDDICB_SUBMITCOMMAND::BroadcastContex"...
0x1800538d4  jmp     short loc_180053896
0x1800538d6  lea     r8, aD3dddicbSubmit_1; "D3DDDICB_SUBMITCOMMAND::BroadcastContex"...
0x1800538dd  jmp     short loc_180053896
0x1800538df  mov     esi, [rdi+224h]
0x1800538e5  cmp     esi, 8
0x1800538e8  jbe     short loc_1800538F3
0x1800538ea  lea     r8, aD3dddicbSubmit_2; "D3DDDICB_SUBMITCOMMAND::NumPrimaries is"...
0x1800538f1  jmp     short loc_180053896
0x1800538f3  cmp     [rdi+268h], ebx
0x1800538f9  jz      short loc_180053914
0x1800538fb  mov     r8, r14; struct CCastableCommandQueue *
0x1800538fe  mov     rdx, rdi; struct _D3DDDICB_SUBMITCOMMAND *
0x180053901  call    ?ETWWriteSubmitCommandCB@CDevice@NDXGI@@QEBAJPEBU_D3DDDICB_SUBMITCOMMAND@@PEAVCCastableCommandQueue@@@Z; NDXGI::CDevice::ETWWriteSubmitCommandCB(_D3DDDICB_SUBMITCOMMAND const *,CCastableCommandQueue *)
0x180053906  test    eax, eax
0x180053908  js      loc_18005387F
0x18005390e  mov     esi, [rdi+224h]
0x180053914  mov     [rsp+1F0h+var_1C0], ebx
0x180053918  xor     edx, edx; Val
0x18005391a  mov     r8d, 180h; Size
0x180053920  lea     rcx, [rsp+1F0h+var_1B0]; void *
0x180053925  call    memset_0
0x18005392a  mov     rax, [rdi]
0x18005392d  mov     [rsp+1F0h+var_1B0], rax
0x180053932  mov     eax, [rdi+8]
0x180053935  mov     [rsp+1F0h+var_1A8], eax
0x180053939  mov     eax, [rdi+0Ch]
0x18005393c  and     eax, 1
0x18005393f  mov     [rsp+1F0h+var_1A4], eax
0x180053943  mov     [rsp+1F0h+var_1A0], rbx
0x180053948  mov     eax, [rdi+10h]
0x18005394b  mov     [rsp+1F0h+var_198], eax
0x18005394f  cmp     [rdi+268h], ebx
0x180053955  jnz     short loc_180053966
0x180053957  mov     [rbp+0F0h+var_38], rbx
0x18005395e  mov     [rbp+0F0h+var_40], ebx
0x180053964  jmp     short loc_1800539A6
0x180053966  mov     eax, [rdi+2A8h]
0x18005396c  test    eax, eax
0x18005396e  jz      short loc_18005398C
0x180053970  mov     [rsp+1F0h+var_1C0], eax
0x180053974  lea     rax, [rsp+1F0h+var_1C0]
0x180053979  mov     [rbp+0F0h+var_38], rax
0x180053980  mov     [rbp+0F0h+var_40], 1
0x18005398a  jmp     short loc_1800539A6
0x18005398c  mov     rax, [rdi+2B0h]
0x180053993  mov     [rbp+0F0h+var_38], rax
0x18005399a  mov     eax, [rdi+2ACh]
0x1800539a0  mov     [rbp+0F0h+var_40], eax
0x1800539a6  mov     [rbp+0F0h+var_84], esi
0x1800539a9  mov     edx, ebx
0x1800539ab  test    esi, esi
0x1800539ad  jz      short loc_1800539C5
0x1800539af  mov     ecx, edx
0x1800539b1  mov     eax, [rdi+rcx*4+228h]
0x1800539b8  mov     [rbp+rcx*4+0F0h+var_80], eax
0x1800539bc  inc     edx
0x1800539be  mov     esi, [rbp+0F0h+var_84]
0x1800539c1  cmp     edx, esi
0x1800539c3  jb      short loc_1800539AF
0x1800539c5  test    r14, r14
0x1800539c8  jz      short loc_1800539F0
0x1800539ca  mov     rax, [r14+138h]
0x1800539d1  mov     rax, [rax]
0x1800539d4  cmp     rax, [r14+138h]
0x1800539db  jz      short loc_1800539F0
0x1800539dd  mov     edx, esi
0x1800539df  mov     ecx, [rax+18h]
0x1800539e2  mov     [rbp+rdx*4+0F0h+var_80], ecx
0x1800539e6  mov     esi, [rbp+0F0h+var_84]
0x1800539e9  inc     esi
0x1800539eb  mov     [rbp+0F0h+var_84], esi
0x1800539ee  jmp     short loc_1800539D1
0x1800539f0  mov     r8d, ebx
0x1800539f3  cmp     [rsp+1F0h+var_198], ebx
0x1800539f7  jbe     short loc_180053A12
0x1800539f9  mov     edx, r8d
0x1800539fc  mov     rax, [rdi+rdx*8+18h]
0x180053a01  mov     ecx, [rax+18h]
0x180053a04  mov     [rsp+rdx*4+1F0h+var_194], ecx
0x180053a08  inc     r8d
0x180053a0b  cmp     r8d, [rsp+1F0h+var_198]
0x180053a10  jb      short loc_1800539F9
0x180053a12  mov     rax, [rdi+218h]
0x180053a19  mov     [rbp+0F0h+var_90], rax
0x180053a1d  mov     eax, [rdi+220h]
0x180053a23  mov     [rbp+0F0h+var_88], eax
0x180053a26  mov     eax, [r15+548h]
0x180053a2d  test    eax, eax
0x180053a2f  jns     short loc_180053A35
0x180053a31  mov     eax, ebx
0x180053a33  jmp     short loc_180053A78
0x180053a35  lea     r9, [rsp+1F0h+var_1B0]
0x180053a3a  mov     rcx, cs:__imp_D3DKMTSubmitCommand
0x180053a41  call    ??$CallAndLogImpl@P6AJPEBU_D3DKMT_SUBMITCOMMAND@@@ZPEAU1@@@YAJP6AJPEBU_D3DKMT_SUBMITCOMMAND@@@ZPEBDP6A?AW4RecordStatusFilterResult@@J@ZPEAU0@@Z; CallAndLogImpl<long (*)(_D3DKMT_SUBMITCOMMAND const *),_D3DKMT_SUBMITCOMMAND *>(long (*)(_D3DKMT_SUBMITCOMMAND const *),char const *,RecordStatusFilterResult (*)(long),_D3DKMT_SUBMITCOMMAND *)
0x180053a46  mov     edi, eax
0x180053a48  xor     r8d, r8d
0x180053a4b  mov     edx, eax
0x180053a4d  mov     rcx, r15
0x180053a50  call    ?NTStatusToHResult@CDevice@NDXGI@@QEAAJJW4EErrorTranslationBehavior@2@@Z; NDXGI::CDevice::NTStatusToHResult(long,NDXGI::EErrorTranslationBehavior)
0x180053a55  test    eax, eax
0x180053a57  jns     short loc_180053A78
0x180053a59  cmp     edi, 0C0000022h
0x180053a5f  jnz     short loc_180053A70
0x180053a61  mov     edx, 887A002Bh; int
0x180053a66  mov     rcx, r15; this
0x180053a69  call    ?RemoveDevice@CDevice@NDXGI@@QEAAXJ@Z; NDXGI::CDevice::RemoveDevice(long)
0x180053a6e  jmp     short loc_180053A31
0x180053a70  cmp     eax, 88760870h
0x180053a75  cmovz   eax, ebx
0x180053a78  mov     rcx, [rbp+0F0h+var_30]
0x180053a7f  xor     rcx, rsp; StackCookie
0x180053a82  call    __security_check_cookie
0x180053a87  mov     rbx, [rsp+1F0h+arg_10]
0x180053a8f  add     rsp, 1D0h
0x180053a96  pop     r15
0x180053a98  pop     r14
0x180053a9a  pop     rdi
0x180053a9b  pop     rsi
0x180053a9c  pop     rbp
0x180053a9d  retn
```
