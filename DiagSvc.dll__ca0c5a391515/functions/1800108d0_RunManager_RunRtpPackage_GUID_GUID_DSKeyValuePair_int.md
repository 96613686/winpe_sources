# RunManager::RunRtpPackage(_GUID,_GUID,DSKeyValuePair * *,int *)

- ea: `0x1800108d0`
- end: `0x180010bbc`
- name: `?RunRtpPackage@RunManager@@MEAAJU_GUID@@0PEAPEAUDSKeyValuePair@@PEAH@Z`
- size: `748`
- prototype: `__int64 __fastcall(__int64 **this, struct _GUID *, struct _GUID *, struct DSKeyValuePair **, int *)`
- caller_count: `0`
- callee_count: `9`
- tags: ``

## callees

- `0x180001720`
- `0x180001e7c`
- `0x180003fc0`
- `0x180004b78`
- `0x1800108d0`
- `0x1800112d0`
- `0x18001134c`
- `0x1800127a8`
- `0x180027010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_calloc` at `0x180010a10`
- `api-ms-win-crt-private-l1-1-0!_o_calloc` at `0x180010a10`
- `api-ms-win-core-file-l1-2-3!GetTempPath2W` at `0x1800109af`
- `api-ms-win-core-file-l1-2-3!GetTempPath2W` at `0x1800109af`

## string_xrefs

- `0x180010b2f`: `Failed to GetTempPath`

## pseudocode

```c
__int64 __fastcall RunManager::RunRtpPackage(
        __int64 **this,
        struct _GUID *a2,
        struct _GUID *a3,
        struct DSKeyValuePair **a4,
        int *a5)
{
  int v9; // edi
  __int64 *v10; // rcx
  __int64 *v11; // r9
  __int128 v12; // xmm1
  __int64 v13; // rax
  __int64 (__fastcall *v14)(__int64 *, __int128 *, __int128 *, __int64 *, __int64 *); // rax
  unsigned __int64 v15; // rdx
  int v16; // ebx
  struct DSKeyValuePair *v17; // rax
  __int64 v18; // rdx
  __int64 v19; // r8
  __int64 ***v20; // rcx
  struct DSKeyValuePair *v21; // r15
  int v22; // ebx
  __int64 *v23; // r11
  const unsigned __int16 *v24; // rax
  __int64 v25; // rdx
  __int64 v26; // r8
  __int64 v27; // r11
  const unsigned __int16 *v28; // rax
  __int64 *v29; // r11
  __int64 **v30; // rcx
  __int64 *i; // rax
  __int64 *j; // rcx
  int v33; // ecx
  int v34; // r8d
  int v35; // r9d
  __int64 v37; // [rsp+60h] [rbp-A0h] BYREF
  int v38; // [rsp+68h] [rbp-98h] BYREF
  int v39; // [rsp+6Ch] [rbp-94h] BYREF
  char *v40; // [rsp+70h] [rbp-90h] BYREF
  const char *v41; // [rsp+78h] [rbp-88h] BYREF
  const char *v42; // [rsp+80h] [rbp-80h] BYREF
  __int128 v43; // [rsp+90h] [rbp-70h] BYREF
  __int128 v44; // [rsp+A0h] [rbp-60h] BYREF
  unsigned __int16 v45[264]; // [rsp+B0h] [rbp-50h] BYREF

  v37 = 0;
  memset_0(v45, 0, 0x208u);
  if ( a4 && a5 )
  {
    *a4 = 0;
    *a5 = 0;
    v9 = ((__int64 (__fastcall *)(__int64 **))(*this)[15])(this);
    if ( v9 >= 0 )
    {
      v10 = this[10];
      v11 = this[47];
      v12 = (__int128)*a2;
      v13 = *v10;
      v44 = (__int128)*a3;
      v14 = *(__int64 (__fastcall **)(__int64 *, __int128 *, __int128 *, __int64 *, __int64 *))(v13 + 56);
      v43 = v12;
      v9 = v14(v10, &v43, &v44, v11, &v37);
      if ( v9 >= 0 )
      {
        if ( (unsigned int)GetTempPath2W(260, v45) - 1 > 0x103 )
        {
          if ( (unsigned int)dword_180039000 > 5 && (unsigned __int8)tlgKeywordOn() )
          {
            v38 = 612;
            v40 = (char *)(this + 14);
            v39 = v9;
            v41 = "onecoreuap\\base\\diagnosis\\pdi\\diagsvc\\engine\\runmanager\\lib\\runmanager.cpp";
            v42 = "RunManager::RunRtpPackage";
            *(_QWORD *)&v43 = "Failed to GetTempPath";
            *(_QWORD *)&v44 = (char *)this + 241;
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
              v33,
              (unsigned int)&dword_18002FE14,
              v34,
              v35,
              (__int64)&v44,
              (__int64)&v39,
              (__int64)&v43,
              (__int64)&v42,
              (__int64)&v41,
              (__int64)&v38,
              (__int64)&v40);
          }
          return (unsigned int)-2147467259;
        }
        else
        {
          v9 = StringCchCatW(v45, v15, L"Gethelp\\");
          if ( v9 >= 0 )
          {
            v9 = (*(__int64 (__fastcall **)(__int64 *, unsigned __int16 *, __int64))(*this[10] + 72))(
                   this[10],
                   v45,
                   v37);
            if ( v9 >= 0 )
            {
              v16 = *(_DWORD *)(v37 + 8);
              v17 = (struct DSKeyValuePair *)calloc(v16, 0x3FCu);
              v20 = (__int64 ***)v37;
              *a4 = v17;
              v21 = v17;
              *a5 = v16;
              v22 = 0;
              v23 = **v20;
              while ( !*((_BYTE *)v23 + 25) )
              {
                v24 = (const unsigned __int16 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(
                                                  v23 + 4,
                                                  v18,
                                                  v19);
                v9 = StringCchCopyW((unsigned __int16 *)v21 + 510 * v22, 0xFFu, v24);
                if ( v9 < 0 )
                  break;
                v28 = (const unsigned __int16 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(
                                                  v27 + 64,
                                                  v25,
                                                  v26);
                v9 = StringCchCopyW((unsigned __int16 *)v21 + 510 * v22 + 255, 0xFFu, v28);
                if ( v9 < 0 )
                  break;
                v30 = (__int64 **)v29[2];
                ++v22;
                if ( *((_BYTE *)v30 + 25) )
                {
                  for ( i = (__int64 *)v29[1]; !*((_BYTE *)i + 25) && v29 == (__int64 *)i[2]; i = (__int64 *)i[1] )
                    v29 = i;
                  v23 = i;
                }
                else
                {
                  v23 = (__int64 *)v29[2];
                  for ( j = *v30; !*((_BYTE *)j + 25); j = (__int64 *)*j )
                    v23 = j;
                }
              }
            }
          }
        }
      }
    }
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x1800108d0  push    rbp
0x1800108d2  push    rbx
0x1800108d3  push    rsi
0x1800108d4  push    rdi
0x1800108d5  push    r12
0x1800108d7  push    r14
0x1800108d9  push    r15
0x1800108db  lea     rbp, [rsp-1D0h]
0x1800108e3  sub     rsp, 2D0h
0x1800108ea  mov     rax, cs:__security_cookie
0x1800108f1  xor     rax, rsp
0x1800108f4  mov     [rbp+200h+var_40], rax
0x1800108fb  mov     rsi, [rbp+200h+arg_20]
0x180010902  mov     r12, r8
0x180010905  mov     r15, rdx
0x180010908  mov     [rsp+300h+var_2A0], 0
0x180010911  mov     rbx, rcx
0x180010914  xor     edx, edx; Val
0x180010916  mov     r8d, 208h; Size
0x18001091c  lea     rcx, [rbp+200h+var_250]; void *
0x180010920  mov     r14, r9
0x180010923  call    memset_0
0x180010928  test    r14, r14
0x18001092b  jz      loc_180010B94
0x180010931  test    rsi, rsi
0x180010934  jz      loc_180010B94
0x18001093a  mov     qword ptr [r14], 0
0x180010941  mov     rcx, rbx
0x180010944  mov     dword ptr [rsi], 0
0x18001094a  mov     rax, [rbx]
0x18001094d  mov     rax, [rax+78h]
0x180010951  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010956  mov     edi, eax
0x180010958  test    eax, eax
0x18001095a  js      loc_180010B99
0x180010960  mov     rcx, [rbx+50h]
0x180010964  lea     rdx, [rsp+300h+var_2A0]
0x180010969  movups  xmm0, xmmword ptr [r12]
0x18001096e  mov     r9, [rbx+178h]
0x180010975  lea     r8, [rbp+200h+var_260]
0x180010979  movups  xmm1, xmmword ptr [r15]
0x18001097d  mov     rax, [rcx]
0x180010980  mov     [rsp+300h+var_2E0], rdx
0x180010985  lea     rdx, [rbp+200h+var_270]
0x180010989  movdqu  [rbp+200h+var_260], xmm0
0x18001098e  mov     rax, [rax+38h]
0x180010992  movdqu  [rbp+200h+var_270], xmm1
0x180010997  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001099c  mov     edi, eax
0x18001099e  test    eax, eax
0x1800109a0  js      loc_180010B99
0x1800109a6  lea     rdx, [rbp+200h+var_250]
0x1800109aa  mov     ecx, 104h
0x1800109af  call    cs:__imp_GetTempPath2W
0x1800109b5  dec     eax
0x1800109b7  cmp     eax, 103h
0x1800109bc  ja      loc_180010AE0
0x1800109c2  lea     r8, aGethelp_0; "Gethelp\\"
0x1800109c9  lea     rcx, [rbp+200h+var_250]; unsigned __int16 *
0x1800109cd  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800109d2  mov     edi, eax
0x1800109d4  test    eax, eax
0x1800109d6  js      loc_180010B99
0x1800109dc  mov     rcx, [rbx+50h]
0x1800109e0  lea     rdx, [rbp+200h+var_250]
0x1800109e4  mov     r8, [rsp+300h+var_2A0]
0x1800109e9  mov     rax, [rcx]
0x1800109ec  mov     rax, [rax+48h]
0x1800109f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800109f5  mov     edi, eax
0x1800109f7  test    eax, eax
0x1800109f9  js      loc_180010B99
0x1800109ff  mov     rax, [rsp+300h+var_2A0]
0x180010a04  mov     edx, 3FCh; Size
0x180010a09  movsxd  rbx, dword ptr [rax+8]
0x180010a0d  mov     rcx, rbx; Count
0x180010a10  call    cs:__imp_calloc
0x180010a16  mov     rcx, [rsp+300h+var_2A0]
0x180010a1b  mov     r12d, 0FFh
0x180010a21  mov     [r14], rax
0x180010a24  mov     r15, rax
0x180010a27  mov     [rsi], ebx
0x180010a29  xor     ebx, ebx
0x180010a2b  mov     r11, [rcx]
0x180010a2e  mov     r11, [r11]
0x180010a31  cmp     byte ptr [r11+19h], 0
0x180010a36  jnz     loc_180010B99
0x180010a3c  lea     rcx, [r11+20h]
0x180010a40  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180010a45  movsxd  rcx, ebx
0x180010a48  mov     r8, rax; unsigned __int16 *
0x180010a4b  imul    r14, rcx, 3FCh
0x180010a52  mov     rdx, r12; unsigned __int64
0x180010a55  add     r14, r15
0x180010a58  mov     rcx, r14; unsigned __int16 *
0x180010a5b  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180010a60  mov     edi, eax
0x180010a62  test    eax, eax
0x180010a64  js      loc_180010B99
0x180010a6a  lea     rcx, [r11+40h]
0x180010a6e  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180010a73  lea     rcx, [r14+1FEh]; unsigned __int16 *
0x180010a7a  mov     r8, rax; unsigned __int16 *
0x180010a7d  mov     rdx, r12; unsigned __int64
0x180010a80  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180010a85  mov     edi, eax
0x180010a87  test    eax, eax
0x180010a89  js      loc_180010B99
0x180010a8f  mov     rcx, [r11+10h]
0x180010a93  inc     ebx
0x180010a95  cmp     byte ptr [rcx+19h], 0
0x180010a99  jz      short loc_180010ABC
0x180010a9b  mov     rax, [r11+8]
0x180010a9f  jmp     short loc_180010AAE
0x180010aa1  cmp     r11, [rax+10h]
0x180010aa5  jnz     short loc_180010AB4
0x180010aa7  mov     r11, rax
0x180010aaa  mov     rax, [rax+8]
0x180010aae  cmp     byte ptr [rax+19h], 0
0x180010ab2  jz      short loc_180010AA1
0x180010ab4  mov     r11, rax
0x180010ab7  jmp     loc_180010A31
0x180010abc  mov     r11, rcx
0x180010abf  mov     rcx, [rcx]
0x180010ac2  cmp     byte ptr [rcx+19h], 0
0x180010ac6  jnz     loc_180010A31
0x180010acc  mov     rax, [rcx]
0x180010acf  mov     r11, rcx
0x180010ad2  mov     rcx, rax
0x180010ad5  cmp     byte ptr [rax+19h], 0
0x180010ad9  jz      short loc_180010ACC
0x180010adb  jmp     loc_180010A31
0x180010ae0  mov     eax, cs:dword_180039000
0x180010ae6  cmp     eax, 5
0x180010ae9  jbe     loc_180010B8D
0x180010aef  call    _tlgKeywordOn
0x180010af4  test    al, al
0x180010af6  jz      loc_180010B8D
0x180010afc  lea     rax, [rbx+70h]
0x180010b00  mov     [rsp+300h+var_298], 264h
0x180010b08  mov     [rsp+300h+var_290], rax
0x180010b0d  lea     rdx, dword_18002FE14
0x180010b14  lea     rax, aOnecoreuapBase_2; "onecoreuap\\base\\diagnosis\\pdi\\diags"...
0x180010b1b  mov     [rsp+300h+var_294], edi
0x180010b1f  mov     [rsp+300h+var_288], rax
0x180010b24  lea     rax, aRunmanagerRunr; "RunManager::RunRtpPackage"
0x180010b2b  mov     [rbp+200h+var_280], rax
0x180010b2f  lea     rax, aFailedToGettem; "Failed to GetTempPath"
0x180010b36  mov     qword ptr [rbp+200h+var_270], rax
0x180010b3a  lea     rax, [rbx+0F1h]
0x180010b41  mov     qword ptr [rbp+200h+var_260], rax
0x180010b45  lea     rax, [rsp+300h+var_290]
0x180010b4a  mov     [rsp+300h+var_2B0], rax
0x180010b4f  lea     rax, [rsp+300h+var_298]
0x180010b54  mov     [rsp+300h+var_2B8], rax
0x180010b59  lea     rax, [rsp+300h+var_288]
0x180010b5e  mov     [rsp+300h+var_2C0], rax
0x180010b63  lea     rax, [rbp+200h+var_280]
0x180010b67  mov     [rsp+300h+var_2C8], rax
0x180010b6c  lea     rax, [rbp+200h+var_270]
0x180010b70  mov     [rsp+300h+var_2D0], rax
0x180010b75  lea     rax, [rsp+300h+var_294]
0x180010b7a  mov     [rsp+300h+var_2D8], rax
0x180010b7f  lea     rax, [rbp+200h+var_260]
0x180010b83  mov     [rsp+300h+var_2E0], rax
0x180010b88  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U1@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@33343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x180010b8d  mov     edi, 80004005h
0x180010b92  jmp     short loc_180010B99
0x180010b94  mov     edi, 80070057h
0x180010b99  mov     eax, edi
0x180010b9b  mov     rcx, [rbp+200h+var_40]
0x180010ba2  xor     rcx, rsp; StackCookie
0x180010ba5  call    __security_check_cookie
0x180010baa  add     rsp, 2D0h
0x180010bb1  pop     r15
0x180010bb3  pop     r14
0x180010bb5  pop     r12
0x180010bb7  pop     rdi
0x180010bb8  pop     rsi
0x180010bb9  pop     rbx
0x180010bba  pop     rbp
0x180010bbb  retn
```
