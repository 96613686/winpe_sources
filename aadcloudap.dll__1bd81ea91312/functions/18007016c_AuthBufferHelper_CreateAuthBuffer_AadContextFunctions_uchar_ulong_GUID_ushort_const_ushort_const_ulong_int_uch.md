# AuthBufferHelper::CreateAuthBuffer(AadContextFunctions *,uchar *,ulong,_GUID,ushort const *,ushort const *,ulong,int,uchar * *,ulong *)

- ea: `0x18007016c`
- end: `0x18007066f`
- name: `?CreateAuthBuffer@AuthBufferHelper@@SAJPEAVAadContextFunctions@@PEAEKU_GUID@@PEBG3KHPEAPEAEPEAK@Z`
- size: `1283`
- prototype: `static int(struct AadContextFunctions *, unsigned __int8 *, unsigned int, struct _GUID *__struct_ptr, const unsigned __int16 *, const unsigned __int16 *, unsigned int, int, unsigned __int8 **, unsigned int *)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18004ac68`

## callees

- `0x1800049d0`
- `0x18000c754`
- `0x18007016c`
- `0x180071118`
- `0x180071e14`
- `0x1800a8010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007034c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180070562`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007034c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180070562`
- `SspiCli!SspiEncryptAuthIdentityEx` at `0x1800704b7`
- `SspiCli!SspiEncryptAuthIdentityEx` at `0x1800704b7`
- `SspiCli!SspiFreeAuthIdentity` at `0x180070645`
- `SspiCli!SspiFreeAuthIdentity` at `0x180070645`
- `SspiCli!SspiLocalFree` at `0x180070632`
- `SspiCli!SspiLocalFree` at `0x180070632`
- `SspiCli!SspiMarshalAuthIdentity` at `0x1800704f8`
- `SspiCli!SspiMarshalAuthIdentity` at `0x1800704f8`
- `SspiCli!SspiCopyAuthIdentity` at `0x180070474`
- `SspiCli!SspiCopyAuthIdentity` at `0x180070474`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall AuthBufferHelper::CreateAuthBuffer(
        struct AadContextFunctions *a1,
        unsigned __int8 *a2,
        unsigned int a3,
        struct _GUID *a4,
        unsigned __int16 *a5,
        unsigned __int16 *a6,
        unsigned int AuthIdentityLength,
        int a8,
        unsigned __int8 **a9,
        unsigned int *a10)
{
  rsize_t v10; // rdi
  int v12; // esi
  unsigned __int64 v13; // rdx
  rsize_t v14; // rax
  int v15; // ecx
  rsize_t v16; // r12
  rsize_t v17; // rcx
  rsize_t v18; // rbx
  char *v19; // r15
  signed int LastError; // eax
  __int16 v21; // ax
  char *v22; // rbx
  char *v23; // rbx
  __int16 v24; // di
  SECURITY_STATUS v25; // eax
  SECURITY_STATUS v26; // ecx
  SECURITY_STATUS v27; // eax
  rsize_t v28; // rbx
  char *v29; // rdi
  signed int v30; // eax
  unsigned int v31; // ebx
  int v33; // [rsp+38h] [rbp-51h]
  int v34; // [rsp+38h] [rbp-51h]
  char *AuthIdentityByteArray; // [rsp+58h] [rbp-31h] BYREF
  rsize_t SourceSize; // [rsp+60h] [rbp-29h] BYREF
  rsize_t DestinationSize; // [rsp+68h] [rbp-21h] BYREF
  char *v38; // [rsp+70h] [rbp-19h] BYREF
  rsize_t v39; // [rsp+78h] [rbp-11h]
  struct AadContextFunctions *v40; // [rsp+80h] [rbp-9h]
  PSEC_WINNT_AUTH_IDENTITY_OPAQUE AuthDataCopy; // [rsp+D8h] [rbp+4Fh] BYREF
  void *Source; // [rsp+E0h] [rbp+57h]
  unsigned int v43; // [rsp+E8h] [rbp+5Fh]
  struct _GUID *v44; // [rsp+F0h] [rbp+67h]

  v44 = a4;
  v43 = a3;
  Source = a2;
  v10 = a3;
  DestinationSize = 0;
  SourceSize = 0;
  AuthDataCopy = 0;
  v38 = 0;
  v40 = a1;
  v39 = 0;
  AuthIdentityByteArray = 0;
  *a9 = 0;
  *a10 = 0;
  if ( a1 )
  {
    v12 = StringCbLengthW(a5, (unsigned __int64)a2, &DestinationSize);
    if ( v12 < 0 )
    {
      v33 = 35;
      goto LABEL_3;
    }
    v12 = StringCbLengthW(a6, v13, &SourceSize);
    if ( v12 < 0 )
    {
      v33 = 36;
      goto LABEL_3;
    }
    v14 = v10 + 92;
    if ( v10 + 92 >= v10 )
    {
      v16 = DestinationSize;
      v17 = v14 + DestinationSize;
      if ( v14 + DestinationSize >= DestinationSize )
      {
        v18 = v17 + SourceSize;
        if ( v17 + SourceSize < SourceSize )
        {
          v12 = -2147024362;
          WPPTraceLogA(2, 1, "%x 0x%08x %s:%u : %s:%ws", 2, -2147024362, "authbuffer.cpp", 48, "HRESULT", &base);
          goto LABEL_37;
        }
        v12 = 0;
        DestinationSize = (unsigned int)v18;
        v19 = (char *)(*(__int64 (__fastcall **)(struct AadContextFunctions *, __int64, _QWORD))(*(_QWORD *)a1 + 8LL))(
                        a1,
                        64,
                        (unsigned int)v18);
        Auto<unsigned short *,ZeroMemoryFunctor<unsigned short *>,AadContextFunctions>::Clear(&v38);
        v38 = v19;
        v39 = v18;
        if ( !v19 )
        {
          LastError = GetLastError();
          v12 = LastError;
          if ( LastError > 0 )
            v12 = (unsigned __int16)LastError | 0x80070000;
          if ( v12 < 0 )
          {
            v33 = 53;
            goto LABEL_3;
          }
        }
        *(_DWORD *)v19 = 513;
        *((_WORD *)v19 + 2) = 48;
        *((_DWORD *)v19 + 2) = DestinationSize;
        *(_QWORD *)(v19 + 36) = 0;
        *((_WORD *)v19 + 22) = 0;
        *((_WORD *)v19 + 24) = 28;
        *((_WORD *)v19 + 25) = v10 + 44;
        *(struct _GUID *)(v19 + 52) = *v44;
        *((_WORD *)v19 + 16) = v10 + 44;
        *((_DWORD *)v19 + 7) = 48;
        *((_WORD *)v19 + 38) = 16;
        v21 = v43 + 16;
        *((_WORD *)v19 + 39) = v43 + 16;
        *((_DWORD *)v19 + 22) = 0;
        *((_WORD *)v19 + 36) = v21;
        *((_DWORD *)v19 + 17) = 28;
        memcpy_s(v19 + 92, v10, Source, v10);
        *((_WORD *)v19 + 42) = v43;
        *((_DWORD *)v19 + 20) = 16;
        v22 = &v19[v10 + 92];
        memcpy_s(v22, v16, a5, v16);
        *((_WORD *)v19 + 8) = v16;
        *((_DWORD *)v19 + 3) = v10 + 92;
        v23 = &v22[v16];
        v24 = SourceSize;
        memcpy_s(v23, SourceSize, a6, SourceSize);
        *((_WORD *)v19 + 12) = v24;
        *((_DWORD *)v19 + 5) = (_DWORD)v23 - (_DWORD)v19;
        AuthIdentityLength = 0;
        v25 = SspiCopyAuthIdentity(v19, &AuthDataCopy);
        if ( v25 < 0 )
        {
          v12 = v25 | 0x10000000;
          v33 = 152;
          goto LABEL_3;
        }
        v26 = SspiEncryptAuthIdentityEx(4u, AuthDataCopy);
        if ( v26 >= 0 || (v15 = v26 | 0x10000000, v15 >= 0) )
        {
          v27 = SspiMarshalAuthIdentity(AuthDataCopy, &AuthIdentityLength, &AuthIdentityByteArray);
          if ( v27 >= 0 )
          {
            v28 = AuthIdentityLength;
            v29 = (char *)(*(__int64 (__fastcall **)(struct AadContextFunctions *, __int64, _QWORD))(*(_QWORD *)a1 + 8LL))(
                            a1,
                            64,
                            AuthIdentityLength);
            Auto<unsigned short *,ZeroMemoryFunctor<unsigned short *>,AadContextFunctions>::Clear(&v38);
            v38 = v29;
            v39 = v28;
            if ( v29 )
              goto LABEL_35;
            v30 = GetLastError();
            v12 = v30;
            if ( v30 > 0 )
              v12 = (unsigned __int16)v30 | 0x80070000;
            if ( v12 >= 0 )
            {
LABEL_35:
              v31 = AuthIdentityLength;
              memcpy_s(v29, AuthIdentityLength, AuthIdentityByteArray, AuthIdentityLength);
              v38 = 0;
              v39 = 0;
              *a9 = (unsigned __int8 *)v29;
              *a10 = v31;
              goto LABEL_37;
            }
            v33 = 174;
          }
          else
          {
            v12 = v27 | 0x10000000;
            v33 = 164;
          }
          goto LABEL_3;
        }
        v34 = 158;
LABEL_12:
        WPPTraceLogA(2, 1, "%x 0x%08x %s:%u : %s:%ws", 2, v15, "authbuffer.cpp", v34, "HRESULT", &base);
        goto LABEL_37;
      }
      v34 = 46;
    }
    else
    {
      v34 = 44;
    }
    v15 = -2147024362;
    v12 = -2147024362;
    goto LABEL_12;
  }
  v12 = -2147024809;
  v33 = 32;
LABEL_3:
  WPPTraceLogA(2, 1, "%x 0x%08x %s:%u : %s:%ws", 2, v12, "authbuffer.cpp", v33, "HRESULT", &base);
LABEL_37:
  if ( AuthIdentityByteArray )
  {
    SspiLocalFree(AuthIdentityByteArray);
    AuthIdentityByteArray = 0;
  }
  if ( AuthDataCopy )
  {
    SspiFreeAuthIdentity(AuthDataCopy);
    AuthDataCopy = 0;
  }
  Auto<unsigned short *,ZeroMemoryFunctor<unsigned short *>,AadContextFunctions>::Clear(&v38);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x18007016c  mov     rax, rsp
0x18007016f  mov     [rax+20h], r9
0x180070173  mov     [rax+18h], r8d
0x180070177  mov     [rax+10h], rdx
0x18007017b  push    rbp
0x18007017c  push    rbx
0x18007017d  push    rsi
0x18007017e  push    rdi
0x18007017f  push    r12
0x180070181  push    r13
0x180070183  push    r14
0x180070185  push    r15
0x180070187  lea     rbp, [rax-47h]
0x18007018b  sub     rsp, 88h
0x180070192  mov     edi, r8d
0x180070195  mov     r14, rcx
0x180070198  xor     ebx, ebx
0x18007019a  mov     [rbp+3Fh+DestinationSize], rbx
0x18007019e  mov     [rbp+3Fh+SourceSize], rbx
0x1800701a2  mov     [rbp+3Fh+AuthDataCopy], rbx
0x1800701a6  mov     [rbp+3Fh+var_58], rbx
0x1800701aa  mov     [rbp+3Fh+var_48], rcx
0x1800701ae  mov     [rbp+3Fh+var_50], rbx
0x1800701b2  mov     [rbp+3Fh+AuthIdentityByteArray], rbx
0x1800701b6  mov     rax, [rbp+3Fh+arg_40]
0x1800701bd  mov     [rax], rbx
0x1800701c0  mov     rax, [rbp+3Fh+arg_48]
0x1800701c7  mov     [rax], ebx
0x1800701c9  test    rcx, rcx
0x1800701cc  jnz     short loc_18007021F
0x1800701ce  mov     esi, 80070057h
0x1800701d3  lea     rax, base
0x1800701da  mov     [rsp+40h], rax
0x1800701df  lea     rax, aHresult; "HRESULT"
0x1800701e6  mov     [rsp+0C0h+var_88], rax
0x1800701eb  mov     dword ptr [rsp+0C0h+var_90], 20h ; ' '
0x1800701f3  lea     rax, aOnecoreuapDsEx_39+25h; "authbuffer.cpp"
0x1800701fa  mov     qword ptr [rsp+0C0h+var_98], rax
0x1800701ff  mov     dword ptr [rsp+0C0h+var_A0], esi
0x180070203  mov     ecx, 2
0x180070208  mov     r9d, ecx
0x18007020b  lea     r8, aX0x08xSUSWs; "%x 0x%08x %s:%u : %s:%ws"
0x180070212  lea     edx, [rcx-1]
0x180070215  call    ?WPPTraceLogA@@YAXKW4AadTracingEventType@@PEBDZZ; WPPTraceLogA(ulong,AadTracingEventType,char const *,...)
0x18007021a  jmp     loc_180070629
0x18007021f  lea     r8, [rbp+3Fh+DestinationSize]; unsigned __int64 *
0x180070223  mov     rcx, [rbp+3Fh+arg_20]; unsigned __int16 *
0x180070227  call    ?StringCbLengthW@@YAJPEBG_KPEA_K@Z; StringCbLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x18007022c  mov     esi, eax
0x18007022e  test    eax, eax
0x180070230  jns     short loc_180070254
0x180070232  lea     rax, base
0x180070239  mov     [rsp+40h], rax
0x18007023e  lea     rax, aHresult; "HRESULT"
0x180070245  mov     [rsp+0C0h+var_88], rax
0x18007024a  mov     dword ptr [rsp+0C0h+var_90], 23h ; '#'
0x180070252  jmp     short loc_1800701F3
0x180070254  lea     r8, [rbp+3Fh+SourceSize]; unsigned __int64 *
0x180070258  mov     rcx, [rbp+3Fh+arg_28]; unsigned __int16 *
0x18007025c  call    ?StringCbLengthW@@YAJPEBG_KPEA_K@Z; StringCbLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x180070261  mov     esi, eax
0x180070263  test    eax, eax
0x180070265  jns     short loc_18007028C
0x180070267  lea     rax, base
0x18007026e  mov     [rsp+40h], rax
0x180070273  lea     rax, aHresult; "HRESULT"
0x18007027a  mov     [rsp+0C0h+var_88], rax
0x18007027f  mov     dword ptr [rsp+0C0h+var_90], 24h ; '$'
0x180070287  jmp     loc_1800701F3
0x18007028c  mov     r13, rdi
0x18007028f  lea     rax, [rdi+5Ch]
0x180070293  cmp     rax, rdi
0x180070296  jnb     short loc_1800702D4
0x180070298  lea     rax, base
0x18007029f  mov     [rsp+40h], rax
0x1800702a4  lea     rax, aHresult; "HRESULT"
0x1800702ab  mov     [rsp+0C0h+var_88], rax
0x1800702b0  mov     dword ptr [rsp+0C0h+var_90], 2Ch ; ','
0x1800702b8  mov     ecx, 80070216h
0x1800702bd  mov     esi, ecx
0x1800702bf  lea     rax, aOnecoreuapDsEx_39+25h; "authbuffer.cpp"
0x1800702c6  mov     qword ptr [rsp+0C0h+var_98], rax
0x1800702cb  mov     dword ptr [rsp+0C0h+var_A0], ecx
0x1800702cf  jmp     loc_180070203
0x1800702d4  mov     r12, [rbp+3Fh+DestinationSize]
0x1800702d8  lea     rcx, [rax+r12]
0x1800702dc  cmp     rcx, r12
0x1800702df  jnb     short loc_180070303
0x1800702e1  lea     rax, base
0x1800702e8  mov     [rsp+40h], rax
0x1800702ed  lea     rax, aHresult; "HRESULT"
0x1800702f4  mov     [rsp+0C0h+var_88], rax
0x1800702f9  mov     dword ptr [rsp+0C0h+var_90], 2Eh ; '.'
0x180070301  jmp     short loc_1800702B8
0x180070303  mov     rax, [rbp+3Fh+SourceSize]
0x180070307  lea     rbx, [rcx+rax]
0x18007030b  cmp     rbx, rax
0x18007030e  jb      loc_1800705D9
0x180070314  xor     esi, esi
0x180070316  mov     ecx, ebx
0x180070318  mov     [rbp+3Fh+DestinationSize], rcx
0x18007031c  mov     rax, [r14]
0x18007031f  mov     r8d, ebx
0x180070322  lea     edx, [rsi+40h]
0x180070325  mov     rcx, r14
0x180070328  mov     rax, [rax+8]
0x18007032c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180070331  mov     r15, rax
0x180070334  lea     rcx, [rbp+3Fh+var_58]
0x180070338  call    ?Clear@?$Auto@PEAGV?$ZeroMemoryFunctor@PEAG@@VAadContextFunctions@@@@QEAAXXZ; Auto<ushort *,ZeroMemoryFunctor<ushort *>,AadContextFunctions>::Clear(void)
0x18007033d  mov     [rbp+3Fh+var_58], r15
0x180070341  mov     [rbp+3Fh+var_50], rbx
0x180070345  xor     ebx, ebx
0x180070347  test    r15, r15
0x18007034a  jnz     short loc_18007038A
0x18007034c  call    cs:__imp_GetLastError
0x180070352  mov     esi, eax
0x180070354  test    eax, eax
0x180070356  jle     short loc_180070361
0x180070358  movzx   esi, ax
0x18007035b  or      esi, 80070000h
0x180070361  test    esi, esi
0x180070363  jns     short loc_18007038A
0x180070365  lea     rax, base
0x18007036c  mov     [rsp+40h], rax
0x180070371  lea     rax, aHresult; "HRESULT"
0x180070378  mov     [rsp+0C0h+var_88], rax
0x18007037d  mov     dword ptr [rsp+0C0h+var_90], 35h ; '5'
0x180070385  jmp     loc_1800701F3
0x18007038a  mov     dword ptr [r15], 201h
0x180070391  mov     word ptr [r15+4], 30h ; '0'
0x180070398  mov     rax, [rbp+3Fh+DestinationSize]
0x18007039c  mov     [r15+8], eax
0x1800703a0  mov     [r15+24h], rbx
0x1800703a4  mov     [r15+2Ch], bx
0x1800703a9  lea     rcx, [r15+30h]
0x1800703ad  mov     word ptr [rcx], 1Ch
0x1800703b2  mov     eax, 2Ch ; ','
0x1800703b7  add     eax, edi
0x1800703b9  mov     [rcx+2], ax
0x1800703bd  mov     rdx, [rbp+3Fh+arg_18]
0x1800703c1  movaps  xmm0, xmmword ptr [rdx]
0x1800703c4  movdqu  xmmword ptr [rcx+4], xmm0
0x1800703c9  mov     [r15+20h], ax
0x1800703ce  mov     eax, ecx
0x1800703d0  sub     eax, r15d
0x1800703d3  mov     [r15+1Ch], eax
0x1800703d7  lea     rdi, [rcx+1Ch]
0x1800703db  mov     edx, 10h
0x1800703e0  mov     [rdi], dx
0x1800703e3  movzx   eax, word ptr [rbp+3Fh+arg_10]
0x1800703e7  add     ax, dx
0x1800703ea  mov     [rdi+2], ax
0x1800703ee  mov     [rdi+0Ch], ebx
0x1800703f1  mov     [rcx+18h], ax
0x1800703f5  mov     eax, edi
0x1800703f7  sub     eax, ecx
0x1800703f9  mov     [rcx+14h], eax
0x1800703fc  lea     rbx, [rdi+10h]
0x180070400  mov     r9, r13; SourceSize
0x180070403  mov     r8, [rbp+3Fh+Source]; Source
0x180070407  mov     rdx, r13; DestinationSize
0x18007040a  mov     rcx, rbx; Destination
0x18007040d  call    memcpy_s
0x180070412  mov     eax, [rbp+3Fh+arg_10]
0x180070415  mov     [rdi+8], ax
0x180070419  mov     eax, ebx
0x18007041b  sub     eax, edi
0x18007041d  mov     [rdi+4], eax
0x180070420  add     rbx, r13
0x180070423  mov     r9, r12; SourceSize
0x180070426  mov     r8, [rbp+3Fh+arg_20]; Source
0x18007042a  mov     rdx, r12; DestinationSize
0x18007042d  mov     rcx, rbx; Destination
0x180070430  call    memcpy_s
0x180070435  mov     [r15+10h], r12w
0x18007043a  mov     eax, ebx
0x18007043c  sub     eax, r15d
0x18007043f  mov     [r15+0Ch], eax
0x180070443  add     rbx, r12
0x180070446  mov     rdi, [rbp+3Fh+SourceSize]
0x18007044a  mov     r9, rdi; SourceSize
0x18007044d  mov     r8, [rbp+3Fh+arg_28]; Source
0x180070451  mov     rdx, rdi; DestinationSize
0x180070454  mov     rcx, rbx; Destination
0x180070457  call    memcpy_s
0x18007045c  mov     [r15+18h], di
0x180070461  sub     ebx, r15d
0x180070464  mov     [r15+14h], ebx
0x180070468  xor     ebx, ebx
0x18007046a  mov     [rbp+3Fh+AuthIdentityLength], ebx
0x18007046d  lea     rdx, [rbp+3Fh+AuthDataCopy]; AuthDataCopy
0x180070471  mov     rcx, r15; AuthData
0x180070474  call    cs:__imp_SspiCopyAuthIdentity
0x18007047a  mov     edi, 10000000h
0x18007047f  test    eax, eax
0x180070481  jns     short loc_1800704AE
0x180070483  mov     esi, eax
0x180070485  or      esi, edi
0x180070487  jge     short loc_1800704AE
0x180070489  lea     rax, base
0x180070490  mov     [rsp+40h], rax
0x180070495  lea     rax, aHresult; "HRESULT"
0x18007049c  mov     [rsp+0C0h+var_88], rax
0x1800704a1  mov     dword ptr [rsp+0C0h+var_90], 98h
0x1800704a9  jmp     loc_1800701F3
0x1800704ae  mov     rdx, [rbp+3Fh+AuthDataCopy]; AuthData
0x1800704b2  mov     ecx, 4; Options
0x1800704b7  call    cs:__imp_SspiEncryptAuthIdentityEx
0x1800704bd  mov     ecx, eax
0x1800704bf  test    eax, eax
0x1800704c1  jns     short loc_1800704EC
0x1800704c3  or      ecx, edi
0x1800704c5  jge     short loc_1800704EC
0x1800704c7  lea     rax, base
0x1800704ce  mov     [rsp+40h], rax
0x1800704d3  lea     rax, aHresult; "HRESULT"
0x1800704da  mov     [rsp+0C0h+var_88], rax
0x1800704df  mov     dword ptr [rsp+0C0h+var_90], 9Eh
0x1800704e7  jmp     loc_1800702BF
0x1800704ec  lea     r8, [rbp+3Fh+AuthIdentityByteArray]; AuthIdentityByteArray
0x1800704f0  lea     rdx, [rbp+3Fh+AuthIdentityLength]; AuthIdentityLength
0x1800704f4  mov     rcx, [rbp+3Fh+AuthDataCopy]; AuthIdentity
0x1800704f8  call    cs:__imp_SspiMarshalAuthIdentity
0x1800704fe  test    eax, eax
0x180070500  jns     short loc_18007052D
0x180070502  mov     esi, eax
0x180070504  or      esi, edi
0x180070506  jge     short loc_18007052D
0x180070508  lea     rax, base
0x18007050f  mov     [rsp+40h], rax
0x180070514  lea     rax, aHresult; "HRESULT"
0x18007051b  mov     [rsp+0C0h+var_88], rax
0x180070520  mov     dword ptr [rsp+0C0h+var_90], 0A4h
0x180070528  jmp     loc_1800701F3
0x18007052d  mov     ebx, [rbp+3Fh+AuthIdentityLength]
0x180070530  mov     rax, [r14]
0x180070533  mov     r8d, ebx
0x180070536  mov     edx, 40h ; '@'
0x18007053b  mov     rcx, r14
0x18007053e  mov     rax, [rax+8]
0x180070542  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180070547  mov     rdi, rax
0x18007054a  lea     rcx, [rbp+3Fh+var_58]
0x18007054e  call    ?Clear@?$Auto@PEAGV?$ZeroMemoryFunctor@PEAG@@VAadContextFunctions@@@@QEAAXXZ; Auto<ushort *,ZeroMemoryFunctor<ushort *>,AadContextFunctions>::Clear(void)
0x180070553  mov     [rbp+3Fh+var_58], rdi
0x180070557  mov     [rbp+3Fh+var_50], rbx
0x18007055b  xor     ebx, ebx
0x18007055d  test    rdi, rdi
0x180070560  jnz     short loc_1800705A0
0x180070562  call    cs:__imp_GetLastError
0x180070568  mov     esi, eax
0x18007056a  test    eax, eax
0x18007056c  jle     short loc_180070577
0x18007056e  movzx   esi, ax
0x180070571  or      esi, 80070000h
0x180070577  test    esi, esi
0x180070579  jns     short loc_1800705A0
0x18007057b  lea     rax, base
0x180070582  mov     [rsp+40h], rax
0x180070587  lea     rax, aHresult; "HRESULT"
0x18007058e  mov     [rsp+0C0h+var_88], rax
0x180070593  mov     dword ptr [rsp+0C0h+var_90], 0AEh
0x18007059b  jmp     loc_1800701F3
0x1800705a0  mov     ebx, [rbp+3Fh+AuthIdentityLength]
0x1800705a3  mov     r9d, ebx; SourceSize
0x1800705a6  mov     r8, [rbp+3Fh+AuthIdentityByteArray]; Source
0x1800705aa  mov     edx, ebx; DestinationSize
0x1800705ac  mov     rcx, rdi; Destination
0x1800705af  call    memcpy_s
0x1800705b4  mov     [rbp+3Fh+var_58], 0
0x1800705bc  mov     [rbp+3Fh+var_50], 0
0x1800705c4  mov     rax, [rbp+3Fh+arg_40]
0x1800705cb  mov     [rax], rdi
0x1800705ce  mov     rax, [rbp+3Fh+arg_48]
0x1800705d5  mov     [rax], ebx
0x1800705d7  jmp     short loc_180070627
0x1800705d9  mov     ecx, 80070216h
0x1800705de  mov     esi, ecx
0x1800705e0  lea     rax, base
0x1800705e7  mov     [rsp+40h], rax
0x1800705ec  lea     rax, aHresult; "HRESULT"
0x1800705f3  mov     [rsp+0C0h+var_88], rax
0x1800705f8  mov     dword ptr [rsp+0C0h+var_90], 30h ; '0'
0x180070600  lea     rax, aOnecoreuapDsEx_39+25h; "authbuffer.cpp"
0x180070607  mov     qword ptr [rsp+0C0h+var_98], rax
0x18007060c  mov     dword ptr [rsp+0C0h+var_A0], ecx
0x180070610  mov     ecx, 2
0x180070615  mov     r9d, ecx
0x180070618  lea     r8, aX0x08xSUSWs; "%x 0x%08x %s:%u : %s:%ws"
0x18007061f  lea     edx, [rcx-1]
0x180070622  call    ?WPPTraceLogA@@YAXKW4AadTracingEventType@@PEBDZZ; WPPTraceLogA(ulong,AadTracingEventType,char const *,...)
0x180070627  xor     ebx, ebx
0x180070629  mov     rcx, [rbp+3Fh+AuthIdentityByteArray]; DataBuffer
0x18007062d  test    rcx, rcx
0x180070630  jz      short loc_18007063C
0x180070632  call    cs:__imp_SspiLocalFree
0x180070638  mov     [rbp+3Fh+AuthIdentityByteArray], rbx
0x18007063c  mov     rcx, [rbp+3Fh+AuthDataCopy]; AuthData
0x180070640  test    rcx, rcx
  ... truncated ...
```
