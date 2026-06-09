# CPreLoadingReferenceFile::ConfigureJetInstancePostInit(void)

- ea: `0x180131fb4`
- end: `0x1801321d8`
- name: `?ConfigureJetInstancePostInit@CPreLoadingReferenceFile@@AEAAKXZ`
- size: `548`
- prototype: `unsigned int __fastcall(CPreLoadingReferenceFile *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x1801327c4`

## callees

- `0x180004374`
- `0x180008290`
- `0x180131fb4`
- `0x18013ab7c`

## import_xrefs

- `ESENT!JetSetSystemParameterW` at `0x1801320f9`
- `ESENT!JetSetSystemParameterW` at `0x18013214d`
- `ESENT!JetSetSystemParameterW` at `0x18013218b`
- `ESENT!JetSetSystemParameterW` at `0x1801320f9`
- `ESENT!JetSetSystemParameterW` at `0x18013214d`
- `ESENT!JetSetSystemParameterW` at `0x18013218b`

## pseudocode

```c
__int64 __fastcall CPreLoadingReferenceFile::ConfigureJetInstancePostInit(CPreLoadingReferenceFile *this)
{
  CHostedCacheMsgEncoding *v2; // rcx
  JET_INSTANCE *v3; // rdi
  unsigned int v4; // ebx
  CHostedCacheMsgEncoding *v5; // rcx
  __int64 v6; // rdx
  int v7; // ecx
  unsigned int v8; // ebx
  unsigned int v9; // eax
  unsigned int v10; // edi

  v2 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 47, WPP_dddfbaf8e29833ad8f504afc37c7cea8_Traceguids);
      v2 = WPP_GLOBAL_Control;
    }
    if ( v2 != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control )
    {
      if ( (*((_BYTE *)v2 + 108) & 4) != 0 && *((_BYTE *)v2 + 105) >= 3u )
      {
        WPP_SF_(*((_QWORD *)v2 + 12), 48, WPP_dddfbaf8e29833ad8f504afc37c7cea8_Traceguids);
        v2 = WPP_GLOBAL_Control;
      }
      if ( v2 != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control )
      {
        if ( (*((_BYTE *)v2 + 108) & 4) != 0 && *((_BYTE *)v2 + 105) >= 3u )
        {
          WPP_SF_(*((_QWORD *)v2 + 12), 49, WPP_dddfbaf8e29833ad8f504afc37c7cea8_Traceguids);
          v2 = WPP_GLOBAL_Control;
        }
        if ( v2 != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control )
        {
          if ( (*((_BYTE *)v2 + 108) & 4) != 0 && *((_BYTE *)v2 + 105) >= 3u )
          {
            WPP_SF_d(*((_QWORD *)v2 + 12), 50, WPP_dddfbaf8e29833ad8f504afc37c7cea8_Traceguids, 1024);
            v2 = WPP_GLOBAL_Control;
          }
          if ( v2 != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control )
          {
            if ( (*((_BYTE *)v2 + 108) & 4) != 0 && *((_BYTE *)v2 + 105) >= 3u )
            {
              WPP_SF_d(*((_QWORD *)v2 + 12), 51, WPP_dddfbaf8e29833ad8f504afc37c7cea8_Traceguids, 1024);
              v2 = WPP_GLOBAL_Control;
            }
            if ( v2 != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
              && (*((_BYTE *)v2 + 108) & 4) != 0
              && *((_BYTE *)v2 + 105) >= 3u )
            {
              WPP_SF_(*((_QWORD *)v2 + 12), 52, WPP_dddfbaf8e29833ad8f504afc37c7cea8_Traceguids);
            }
          }
        }
      }
    }
  }
  v3 = (JET_INSTANCE *)((char *)this + 3776);
  v4 = JetSetSystemParameterW(v3, 0, 0x10u, 1u, 0);
  if ( v4 )
  {
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) == 0
      || !*((_BYTE *)WPP_GLOBAL_Control + 105) )
    {
      goto LABEL_31;
    }
    v6 = 53;
LABEL_30:
    WPP_SF_d(*((_QWORD *)v5 + 12), v6, WPP_dddfbaf8e29833ad8f504afc37c7cea8_Traceguids, v4);
LABEL_31:
    v7 = v4;
    return TranslateJetError(v7);
  }
  v4 = JetSetSystemParameterW(v3, 0, 0x3Cu, 0x400u, 0);
  if ( v4 )
  {
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) == 0
      || !*((_BYTE *)WPP_GLOBAL_Control + 105) )
    {
      goto LABEL_31;
    }
    v6 = 54;
    goto LABEL_30;
  }
  v8 = 0;
  v9 = JetSetSystemParameterW(v3, 0, 0x17u, 0x400u, 0);
  v10 = v9;
  if ( v9 )
  {
    if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 105) )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 12), 55, WPP_dddfbaf8e29833ad8f504afc37c7cea8_Traceguids, v9);
    }
    v7 = v10;
    return TranslateJetError(v7);
  }
  return v8;
}

```

## disassembly

```asm
0x180131fb4  push    rbx
0x180131fb6  push    rbp
0x180131fb7  push    rdi
0x180131fb8  push    r13
0x180131fba  push    r14
0x180131fbc  sub     rsp, 30h
0x180131fc0  mov     rdi, rcx
0x180131fc3  mov     rcx, cs:WPP_GLOBAL_Control
0x180131fca  lea     rbp, WPP_GLOBAL_Control
0x180131fd1  lea     r14, WPP_dddfbaf8e29833ad8f504afc37c7cea8_Traceguids
0x180131fd8  mov     r13d, 400h
0x180131fde  cmp     rcx, rbp
0x180131fe1  jz      loc_1801320DC
0x180131fe7  test    byte ptr [rcx+6Ch], 4
0x180131feb  jz      short loc_18013200B
0x180131fed  cmp     byte ptr [rcx+69h], 4
0x180131ff1  jb      short loc_18013200B
0x180131ff3  mov     rcx, [rcx+60h]
0x180131ff7  mov     edx, 2Fh ; '/'
0x180131ffc  mov     r8, r14
0x180131fff  call    WPP_SF_
0x180132004  mov     rcx, cs:WPP_GLOBAL_Control
0x18013200b  cmp     rcx, rbp
0x18013200e  jz      loc_1801320DC
0x180132014  test    byte ptr [rcx+6Ch], 4
0x180132018  mov     bl, 3
0x18013201a  jz      short loc_180132039
0x18013201c  cmp     [rcx+69h], bl
0x18013201f  jb      short loc_180132039
0x180132021  mov     rcx, [rcx+60h]
0x180132025  mov     edx, 30h ; '0'
0x18013202a  mov     r8, r14
0x18013202d  call    WPP_SF_
0x180132032  mov     rcx, cs:WPP_GLOBAL_Control
0x180132039  cmp     rcx, rbp
0x18013203c  jz      loc_1801320DC
0x180132042  test    byte ptr [rcx+6Ch], 4
0x180132046  jz      short loc_180132065
0x180132048  cmp     [rcx+69h], bl
0x18013204b  jb      short loc_180132065
0x18013204d  mov     rcx, [rcx+60h]
0x180132051  mov     edx, 31h ; '1'
0x180132056  mov     r8, r14
0x180132059  call    WPP_SF_
0x18013205e  mov     rcx, cs:WPP_GLOBAL_Control
0x180132065  cmp     rcx, rbp
0x180132068  jz      short loc_1801320DC
0x18013206a  test    byte ptr [rcx+6Ch], 4
0x18013206e  jz      short loc_180132090
0x180132070  cmp     [rcx+69h], bl
0x180132073  jb      short loc_180132090
0x180132075  mov     rcx, [rcx+60h]
0x180132079  mov     edx, 32h ; '2'
0x18013207e  mov     r9d, r13d
0x180132081  mov     r8, r14
0x180132084  call    WPP_SF_d
0x180132089  mov     rcx, cs:WPP_GLOBAL_Control
0x180132090  cmp     rcx, rbp
0x180132093  jz      short loc_1801320DC
0x180132095  test    byte ptr [rcx+6Ch], 4
0x180132099  jz      short loc_1801320BB
0x18013209b  cmp     [rcx+69h], bl
0x18013209e  jb      short loc_1801320BB
0x1801320a0  mov     rcx, [rcx+60h]
0x1801320a4  mov     edx, 33h ; '3'
0x1801320a9  mov     r9d, r13d
0x1801320ac  mov     r8, r14
0x1801320af  call    WPP_SF_d
0x1801320b4  mov     rcx, cs:WPP_GLOBAL_Control
0x1801320bb  cmp     rcx, rbp
0x1801320be  jz      short loc_1801320DC
0x1801320c0  test    byte ptr [rcx+6Ch], 4
0x1801320c4  jz      short loc_1801320DC
0x1801320c6  cmp     [rcx+69h], bl
0x1801320c9  jb      short loc_1801320DC
0x1801320cb  mov     rcx, [rcx+60h]
0x1801320cf  mov     edx, 34h ; '4'
0x1801320d4  mov     r8, r14
0x1801320d7  call    WPP_SF_
0x1801320dc  xor     edx, edx; sesid
0x1801320de  mov     [rsp+58h+szParam], 0; szParam
0x1801320e7  add     rdi, 0EC0h
0x1801320ee  mov     rcx, rdi; pinstance
0x1801320f1  lea     r9d, [rdx+1]; lParam
0x1801320f5  lea     r8d, [rdx+10h]; paramid
0x1801320f9  call    cs:__imp_JetSetSystemParameterW
0x1801320ff  mov     ebx, eax
0x180132101  test    eax, eax
0x180132103  jz      short loc_180132138
0x180132105  mov     rcx, cs:WPP_GLOBAL_Control
0x18013210c  cmp     rcx, rbp
0x18013210f  jz      short loc_180132131
0x180132111  test    byte ptr [rcx+6Ch], 4
0x180132115  jz      short loc_180132131
0x180132117  cmp     byte ptr [rcx+69h], 1
0x18013211b  jb      short loc_180132131
0x18013211d  mov     edx, 35h ; '5'
0x180132122  mov     rcx, [rcx+60h]
0x180132126  mov     r9d, ebx
0x180132129  mov     r8, r14
0x18013212c  call    WPP_SF_d
0x180132131  mov     ecx, ebx
0x180132133  jmp     loc_1801321C3
0x180132138  xor     edx, edx; sesid
0x18013213a  mov     [rsp+58h+szParam], 0; szParam
0x180132143  mov     r9, r13; lParam
0x180132146  mov     rcx, rdi; pinstance
0x180132149  lea     r8d, [rdx+3Ch]; paramid
0x18013214d  call    cs:__imp_JetSetSystemParameterW
0x180132153  mov     ebx, eax
0x180132155  test    eax, eax
0x180132157  jz      short loc_180132178
0x180132159  mov     rcx, cs:WPP_GLOBAL_Control
0x180132160  cmp     rcx, rbp
0x180132163  jz      short loc_180132131
0x180132165  test    byte ptr [rcx+6Ch], 4
0x180132169  jz      short loc_180132131
0x18013216b  cmp     byte ptr [rcx+69h], 1
0x18013216f  jb      short loc_180132131
0x180132171  mov     edx, 36h ; '6'
0x180132176  jmp     short loc_180132122
0x180132178  xor     ebx, ebx
0x18013217a  mov     r9, r13; lParam
0x18013217d  xor     edx, edx; sesid
0x18013217f  mov     [rsp+58h+szParam], rbx; szParam
0x180132184  mov     rcx, rdi; pinstance
0x180132187  lea     r8d, [rbx+17h]; paramid
0x18013218b  call    cs:__imp_JetSetSystemParameterW
0x180132191  mov     edi, eax
0x180132193  test    eax, eax
0x180132195  jz      short loc_1801321CA
0x180132197  mov     rcx, cs:WPP_GLOBAL_Control
0x18013219e  cmp     rcx, rbp
0x1801321a1  jz      short loc_1801321C1
0x1801321a3  test    byte ptr [rcx+6Ch], 4
0x1801321a7  jz      short loc_1801321C1
0x1801321a9  cmp     byte ptr [rcx+69h], 1
0x1801321ad  jb      short loc_1801321C1
0x1801321af  mov     rcx, [rcx+60h]
0x1801321b3  lea     edx, [rbx+37h]
0x1801321b6  mov     r9d, eax
0x1801321b9  mov     r8, r14
0x1801321bc  call    WPP_SF_d
0x1801321c1  mov     ecx, edi; int
0x1801321c3  call    ?TranslateJetError@@YAKJ@Z; TranslateJetError(long)
0x1801321c8  mov     ebx, eax
0x1801321ca  mov     eax, ebx
0x1801321cc  add     rsp, 30h
0x1801321d0  pop     r14
0x1801321d2  pop     r13
0x1801321d4  pop     rdi
0x1801321d5  pop     rbp
0x1801321d6  pop     rbx
0x1801321d7  retn
```
