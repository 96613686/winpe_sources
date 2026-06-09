# CCachePublication::InitializeForWrite(ushort const *,ushort const *,ushort const *)

- ea: `0x180088478`
- end: `0x180088892`
- name: `?InitializeForWrite@CCachePublication@@QEAAKPEBG00@Z`
- size: `1050`
- prototype: `__int64 __fastcall(CCachePublication *this, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops`

## callers

- `0x1800557d0`

## callees

- `0x1800024fc`
- `0x180008290`
- `0x1800094d4`
- `0x18000cf48`
- `0x180011798`
- `0x1800524e0`
- `0x180087a40`
- `0x180088478`
- `0x180144882`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800885bc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180088611`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008876e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800885bc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180088611`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008876e`
- `KERNEL32!CloseHandle` at `0x180088879`
- `KERNEL32!CloseHandle` at `0x180088879`
- `KERNEL32!CreateFileW` at `0x1800885a9`
- `KERNEL32!CreateFileW` at `0x1800885fa`
- `KERNEL32!CreateFileW` at `0x18008875b`
- `KERNEL32!CreateFileW` at `0x1800885a9`
- `KERNEL32!CreateFileW` at `0x1800885fa`
- `KERNEL32!CreateFileW` at `0x18008875b`

## pseudocode

```c
__int64 __fastcall CCachePublication::InitializeForWrite(
        CCachePublication *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4)
{
  int v8; // eax
  unsigned int v9; // edi
  CHostedCacheMsgEncoding *v10; // rcx
  __int64 v11; // rdx
  __int64 v12; // r9
  int v13; // eax
  HANDLE FileW; // r15
  DWORD LastError; // eax
  HANDLE v16; // rax
  DWORD v17; // eax
  CHostedCacheMsgEncoding *v18; // rcx
  int v19; // edx
  int v20; // r9d
  unsigned int v21; // eax
  int v22; // eax
  HANDLE v23; // rax
  DWORD v24; // eax
  void *v25; // rax
  char dwCreationDisposition; // [rsp+20h] [rbp-68h]

  if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u )
  {
    WPP_SF_qSS(
      *((_QWORD *)WPP_GLOBAL_Control + 12),
      14,
      (unsigned int)WPP_cacbc209fdf435e986c0ff08ed446cf3_Traceguids,
      (_DWORD)this,
      (__int64)a2,
      (__int64)a4);
  }
  v8 = StringCchCopyW((unsigned __int16 *)this + 72, 0x104u, a2);
  if ( v8 < 0 )
  {
    v9 = (unsigned __int16)v8;
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 105) )
    {
      v11 = 15;
LABEL_10:
      v12 = v9;
LABEL_11:
      WPP_SF_d(*((_QWORD *)v10 + 12), v11, WPP_cacbc209fdf435e986c0ff08ed446cf3_Traceguids, v12);
      return v9;
    }
    return v9;
  }
  v13 = StringCchCopyW((unsigned __int16 *)this + 332, 0x104u, a3);
  if ( v13 >= 0 )
  {
    FileW = CreateFileW((LPCWSTR)this + 72, 0xC0000000, 5u, 0, 3u, 0, 0);
    if ( FileW != (HANDLE)-1LL )
    {
      v9 = 4058;
      if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 105) )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 12), 19, WPP_cacbc209fdf435e986c0ff08ed446cf3_Traceguids, 4058);
      }
      CloseHandle(FileW);
      return v9;
    }
    LastError = GetLastError();
    v9 = LastError;
    if ( LastError != 2 )
    {
      if ( LastError == 5 )
      {
        v18 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) == 0
          || !*((_BYTE *)WPP_GLOBAL_Control + 105) )
        {
          return v9;
        }
        v19 = 17;
        dwCreationDisposition = 5;
      }
      else
      {
        v18 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) == 0
          || !*((_BYTE *)WPP_GLOBAL_Control + 105) )
        {
          return v9;
        }
        v19 = 18;
        dwCreationDisposition = LastError;
      }
      v20 = (int)a2;
LABEL_32:
      WPP_SF_Sd(
        *((_QWORD *)v18 + 12),
        v19,
        (unsigned int)WPP_cacbc209fdf435e986c0ff08ed446cf3_Traceguids,
        v20,
        dwCreationDisposition);
      return v9;
    }
    v16 = CreateFileW((LPCWSTR)this + 332, 0xC0010000, 5u, 0, 1u, 0x40000000u, 0);
    *((_QWORD *)this + 213) = v16;
    if ( v16 != (HANDLE)-1LL )
    {
      v21 = ICachePublicationFileHelper::Create(v16, (char *)this + 72);
      v9 = v21;
      if ( v21 )
      {
        v10 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 105) )
        {
          v11 = 22;
          v12 = v21;
          goto LABEL_11;
        }
      }
      else
      {
        v22 = StringCchCopyW((unsigned __int16 *)this + 592, 0x104u, a4);
        if ( v22 >= 0 )
        {
          v23 = CreateFileW(a4, 0xC0000000, 0, 0, 2u, 0x44000000u, 0);
          *((_QWORD *)this + 214) = v23;
          if ( v23 == (HANDLE)-1LL )
          {
            v24 = GetLastError();
            v9 = v24;
            if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 105) )
            {
              WPP_SF_Sd(
                *((_QWORD *)WPP_GLOBAL_Control + 12),
                24,
                (unsigned int)WPP_cacbc209fdf435e986c0ff08ed446cf3_Traceguids,
                (_DWORD)a4,
                v24);
            }
          }
          else
          {
            v25 = operator new[](*((unsigned int *)this + 472));
            std::auto_ptr<unsigned short>::reset((char *)this + 1832, v25);
            memset_0(*((void **)this + 229), 0, *((unsigned int *)this + 472));
            *((_QWORD *)this + 232) = *((_QWORD *)this + 229);
            *((_BYTE *)this + 1777) = 1;
          }
        }
        else
        {
          v9 = (unsigned __int16)v22;
          v10 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 105) )
          {
            v11 = 23;
            goto LABEL_10;
          }
        }
      }
      return v9;
    }
    v17 = GetLastError();
    v9 = v17;
    if ( v17 == 80 )
    {
      v9 = 4058;
    }
    else if ( v17 == 5 )
    {
      v18 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control )
        return v9;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) == 0 || !*((_BYTE *)WPP_GLOBAL_Control + 105) )
        goto LABEL_28;
      WPP_SF_Sd(
        *((_QWORD *)WPP_GLOBAL_Control + 12),
        20,
        (unsigned int)WPP_cacbc209fdf435e986c0ff08ed446cf3_Traceguids,
        (_DWORD)this + 664,
        5);
    }
    v18 = WPP_GLOBAL_Control;
LABEL_28:
    if ( v18 == (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
      || (*((_BYTE *)v18 + 108) & 4) == 0
      || !*((_BYTE *)v18 + 105) )
    {
      return v9;
    }
    v19 = 21;
    dwCreationDisposition = v9;
    v20 = (_DWORD)this + 664;
    goto LABEL_32;
  }
  v9 = (unsigned __int16)v13;
  v10 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 105) )
  {
    v11 = 16;
    goto LABEL_10;
  }
  return v9;
}

```

## disassembly

```asm
0x180088478  push    rbx
0x18008847a  push    rbp
0x18008847b  push    rsi
0x18008847c  push    rdi
0x18008847d  push    r12
0x18008847f  push    r13
0x180088481  push    r14
0x180088483  push    r15
0x180088485  sub     rsp, 48h
0x180088489  mov     rbp, r9
0x18008848c  mov     r15, r8
0x18008848f  mov     rbx, rdx
0x180088492  mov     rsi, rcx
0x180088495  mov     rcx, cs:WPP_GLOBAL_Control
0x18008849c  lea     r13, WPP_GLOBAL_Control
0x1800884a3  mov     r12b, 4
0x1800884a6  cmp     rcx, r13
0x1800884a9  jz      short loc_1800884D9
0x1800884ab  test    [rcx+6Ch], r12b
0x1800884af  jz      short loc_1800884D9
0x1800884b1  cmp     [rcx+69h], r12b
0x1800884b5  jb      short loc_1800884D9
0x1800884b7  mov     rcx, [rcx+60h]
0x1800884bb  lea     r8, WPP_cacbc209fdf435e986c0ff08ed446cf3_Traceguids
0x1800884c2  mov     qword ptr [rsp+88h+dwFlagsAndAttributes], r9
0x1800884c7  mov     edx, 0Eh
0x1800884cc  mov     r9, rsi
0x1800884cf  mov     qword ptr [rsp+88h+dwCreationDisposition], rbx
0x1800884d4  call    WPP_SF_qSS
0x1800884d9  lea     rdi, [rsi+90h]
0x1800884e0  mov     r8, rbx; unsigned __int16 *
0x1800884e3  mov     rcx, rdi; unsigned __int16 *
0x1800884e6  mov     edx, 104h; unsigned __int64
0x1800884eb  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800884f0  test    eax, eax
0x1800884f2  jns     short loc_180088538
0x1800884f4  movzx   edi, ax
0x1800884f7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800884fe  cmp     rcx, r13
0x180088501  jz      loc_18008887F
0x180088507  test    [rcx+6Ch], r12b
0x18008850b  jz      loc_18008887F
0x180088511  cmp     byte ptr [rcx+69h], 1
0x180088515  jb      loc_18008887F
0x18008851b  mov     edx, 0Fh
0x180088520  mov     r9d, edi
0x180088523  mov     rcx, [rcx+60h]
0x180088527  lea     r8, WPP_cacbc209fdf435e986c0ff08ed446cf3_Traceguids
0x18008852e  call    WPP_SF_d
0x180088533  jmp     loc_18008887F
0x180088538  lea     r14, [rsi+298h]
0x18008853f  mov     r8, r15; unsigned __int16 *
0x180088542  mov     rcx, r14; unsigned __int16 *
0x180088545  mov     edx, 104h; unsigned __int64
0x18008854a  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18008854f  test    eax, eax
0x180088551  jns     short loc_180088581
0x180088553  movzx   edi, ax
0x180088556  mov     rcx, cs:WPP_GLOBAL_Control
0x18008855d  cmp     rcx, r13
0x180088560  jz      loc_18008887F
0x180088566  test    [rcx+6Ch], r12b
0x18008856a  jz      loc_18008887F
0x180088570  cmp     byte ptr [rcx+69h], 1
0x180088574  jb      loc_18008887F
0x18008857a  mov     edx, 10h
0x18008857f  jmp     short loc_180088520
0x180088581  xor     r9d, r9d; lpSecurityAttributes
0x180088584  mov     [rsp+88h+hTemplateFile], 0; hTemplateFile
0x18008858d  mov     [rsp+88h+dwFlagsAndAttributes], 0; dwFlagsAndAttributes
0x180088595  mov     edx, 0C0000000h; dwDesiredAccess
0x18008859a  mov     rcx, rdi; lpFileName
0x18008859d  mov     [rsp+88h+dwCreationDisposition], 3; dwCreationDisposition
0x1800885a5  lea     r8d, [r9+5]; dwShareMode
0x1800885a9  call    cs:__imp_CreateFileW
0x1800885af  mov     r15, rax
0x1800885b2  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800885b6  jnz     loc_180088841
0x1800885bc  call    cs:__imp_GetLastError
0x1800885c2  mov     edi, eax
0x1800885c4  mov     r15d, 5
0x1800885ca  cmp     eax, 2
0x1800885cd  jnz     loc_1800887EF
0x1800885d3  mov     [rsp+88h+hTemplateFile], 0; hTemplateFile
0x1800885dc  xor     r9d, r9d; lpSecurityAttributes
0x1800885df  mov     [rsp+88h+dwFlagsAndAttributes], 40000000h; dwFlagsAndAttributes
0x1800885e7  mov     r8d, r15d; dwShareMode
0x1800885ea  mov     edx, 0C0010000h; dwDesiredAccess
0x1800885ef  mov     [rsp+88h+dwCreationDisposition], 1; dwCreationDisposition
0x1800885f7  mov     rcx, r14; lpFileName
0x1800885fa  call    cs:__imp_CreateFileW
0x180088600  mov     [rsi+6A8h], rax
0x180088607  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18008860b  jnz     loc_1800886A8
0x180088611  call    cs:__imp_GetLastError
0x180088617  mov     edi, eax
0x180088619  cmp     eax, 50h ; 'P'
0x18008861c  jnz     short loc_180088625
0x18008861e  mov     edi, 0FDAh
0x180088623  jmp     short loc_180088663
0x180088625  cmp     eax, r15d
0x180088628  jnz     short loc_180088663
0x18008862a  mov     rcx, cs:WPP_GLOBAL_Control
0x180088631  cmp     rcx, r13
0x180088634  jz      loc_18008887F
0x18008863a  test    [rcx+6Ch], r12b
0x18008863e  jz      short loc_18008866A
0x180088640  cmp     byte ptr [rcx+69h], 1
0x180088644  jb      short loc_18008866A
0x180088646  mov     rcx, [rcx+60h]
0x18008864a  lea     r8, WPP_cacbc209fdf435e986c0ff08ed446cf3_Traceguids
0x180088651  mov     edx, 14h
0x180088656  mov     [rsp+88h+dwCreationDisposition], r15d
0x18008865b  mov     r9, r14
0x18008865e  call    WPP_SF_Sd
0x180088663  mov     rcx, cs:WPP_GLOBAL_Control
0x18008866a  cmp     rcx, r13
0x18008866d  jz      loc_18008887F
0x180088673  test    [rcx+6Ch], r12b
0x180088677  jz      loc_18008887F
0x18008867d  cmp     byte ptr [rcx+69h], 1
0x180088681  jb      loc_18008887F
0x180088687  mov     edx, 15h
0x18008868c  mov     [rsp+88h+dwCreationDisposition], edi
0x180088690  mov     r9, r14
0x180088693  mov     rcx, [rcx+60h]
0x180088697  lea     r8, WPP_cacbc209fdf435e986c0ff08ed446cf3_Traceguids
0x18008869e  call    WPP_SF_Sd
0x1800886a3  jmp     loc_18008887F
0x1800886a8  lea     rdx, [rsi+48h]
0x1800886ac  mov     rcx, rax
0x1800886af  call    ?Create@ICachePublicationFileHelper@@SAKPEAXPEAV?$SmartPointer@VICachePublicationFileHelper@@@@@Z; ICachePublicationFileHelper::Create(void *,SmartPointer<ICachePublicationFileHelper> *)
0x1800886b4  mov     edi, eax
0x1800886b6  test    eax, eax
0x1800886b8  jz      short loc_1800886EB
0x1800886ba  mov     rcx, cs:WPP_GLOBAL_Control
0x1800886c1  cmp     rcx, r13
0x1800886c4  jz      loc_18008887F
0x1800886ca  test    [rcx+6Ch], r12b
0x1800886ce  jz      loc_18008887F
0x1800886d4  cmp     byte ptr [rcx+69h], 1
0x1800886d8  jb      loc_18008887F
0x1800886de  mov     edx, 16h
0x1800886e3  mov     r9d, eax
0x1800886e6  jmp     loc_180088523
0x1800886eb  lea     rcx, [rsi+4A0h]; unsigned __int16 *
0x1800886f2  mov     r8, rbp; unsigned __int16 *
0x1800886f5  mov     edx, 104h; unsigned __int64
0x1800886fa  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800886ff  test    eax, eax
0x180088701  jns     short loc_180088734
0x180088703  movzx   edi, ax
0x180088706  mov     rcx, cs:WPP_GLOBAL_Control
0x18008870d  cmp     rcx, r13
0x180088710  jz      loc_18008887F
0x180088716  test    [rcx+6Ch], r12b
0x18008871a  jz      loc_18008887F
0x180088720  cmp     byte ptr [rcx+69h], 1
0x180088724  jb      loc_18008887F
0x18008872a  mov     edx, 17h
0x18008872f  jmp     loc_180088520
0x180088734  mov     [rsp+88h+hTemplateFile], 0; hTemplateFile
0x18008873d  xor     r9d, r9d; lpSecurityAttributes
0x180088740  mov     [rsp+88h+dwFlagsAndAttributes], 44000000h; dwFlagsAndAttributes
0x180088748  xor     r8d, r8d; dwShareMode
0x18008874b  mov     edx, 0C0000000h; dwDesiredAccess
0x180088750  mov     [rsp+88h+dwCreationDisposition], 2; dwCreationDisposition
0x180088758  mov     rcx, rbp; lpFileName
0x18008875b  call    cs:__imp_CreateFileW
0x180088761  mov     [rsi+6B0h], rax
0x180088768  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18008876c  jnz     short loc_1800887AB
0x18008876e  call    cs:__imp_GetLastError
0x180088774  mov     edi, eax
0x180088776  mov     rcx, cs:WPP_GLOBAL_Control
0x18008877d  cmp     rcx, r13
0x180088780  jz      loc_18008887F
0x180088786  test    [rcx+6Ch], r12b
0x18008878a  jz      loc_18008887F
0x180088790  cmp     byte ptr [rcx+69h], 1
0x180088794  jb      loc_18008887F
0x18008879a  mov     edx, 18h
0x18008879f  mov     [rsp+88h+dwCreationDisposition], eax
0x1800887a3  mov     r9, rbp
0x1800887a6  jmp     loc_180088693
0x1800887ab  mov     ecx, [rsi+760h]; unsigned __int64
0x1800887b1  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1800887b6  lea     rbx, [rsi+728h]
0x1800887bd  mov     rdx, rax
0x1800887c0  mov     rcx, rbx
0x1800887c3  call    ?reset@?$auto_ptr@G@std@@QEAAXPEAG@Z; std::auto_ptr<ushort>::reset(ushort *)
0x1800887c8  mov     r8d, [rsi+760h]; Size
0x1800887cf  xor     edx, edx; Val
0x1800887d1  mov     rcx, [rbx]; void *
0x1800887d4  call    memset_0
0x1800887d9  mov     rax, [rbx]
0x1800887dc  mov     [rsi+740h], rax
0x1800887e3  mov     byte ptr [rsi+6F1h], 1
0x1800887ea  jmp     loc_18008887F
0x1800887ef  cmp     eax, r15d
0x1800887f2  jnz     short loc_18008881E
0x1800887f4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800887fb  cmp     rcx, r13
0x1800887fe  jz      short loc_18008887F
0x180088800  test    [rcx+6Ch], r12b
0x180088804  jz      short loc_18008887F
0x180088806  cmp     byte ptr [rcx+69h], 1
0x18008880a  jb      short loc_18008887F
0x18008880c  mov     edx, 11h
0x180088811  mov     [rsp+88h+dwCreationDisposition], r15d
0x180088816  mov     r9, rbx
0x180088819  jmp     loc_180088693
0x18008881e  mov     rcx, cs:WPP_GLOBAL_Control
0x180088825  cmp     rcx, r13
0x180088828  jz      short loc_18008887F
0x18008882a  test    [rcx+6Ch], r12b
0x18008882e  jz      short loc_18008887F
0x180088830  cmp     byte ptr [rcx+69h], 1
0x180088834  jb      short loc_18008887F
0x180088836  mov     edx, 12h
0x18008883b  mov     [rsp+88h+dwCreationDisposition], eax
0x18008883f  jmp     short loc_180088816
0x180088841  mov     edi, 0FDAh
0x180088846  mov     rcx, cs:WPP_GLOBAL_Control
0x18008884d  cmp     rcx, r13
0x180088850  jz      short loc_180088876
0x180088852  test    [rcx+6Ch], r12b
0x180088856  jz      short loc_180088876
0x180088858  cmp     byte ptr [rcx+69h], 1
0x18008885c  jb      short loc_180088876
0x18008885e  mov     rcx, [rcx+60h]
0x180088862  lea     r8, WPP_cacbc209fdf435e986c0ff08ed446cf3_Traceguids
0x180088869  mov     edx, 13h
0x18008886e  mov     r9d, edi
0x180088871  call    WPP_SF_d
0x180088876  mov     rcx, r15; hObject
0x180088879  call    cs:__imp_CloseHandle
0x18008887f  mov     eax, edi
0x180088881  add     rsp, 48h
0x180088885  pop     r15
0x180088887  pop     r14
0x180088889  pop     r13
0x18008888b  pop     r12
0x18008888d  pop     rdi
0x18008888e  pop     rsi
0x18008888f  pop     rbp
0x180088890  pop     rbx
0x180088891  retn
```
