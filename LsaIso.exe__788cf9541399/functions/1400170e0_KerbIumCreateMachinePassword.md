# KerbIumCreateMachinePassword

- ea: `0x1400170e0`
- end: `0x140017449`
- name: `KerbIumCreateMachinePassword`
- size: `873`
- prototype: `__int64 __fastcall(int, int, int, int, __int64, __int64, struct _KERB_ENCRYPTION_KEY *, __int64)`
- caller_count: `0`
- callee_count: `13`
- tags: `registry_config`

## callees

- `0x140002c64`
- `0x140002c84`
- `0x140011964`
- `0x14001212c`
- `0x140014458`
- `0x1400170e0`
- `0x140017d00`
- `0x14001a4a0`
- `0x14001a8c8`
- `0x14001aa2c`
- `0x14001af0c`
- `0x14001be28`
- `0x14001de00`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x140017144`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x140017144`
- `KerbClientShared!KerbClientBuildKerbPriv` at `0x14001732e`
- `KerbClientShared!KerbClientBuildKerbPriv` at `0x14001732e`

## string_xrefs

- `0x140017171`: `KerbIumCreateMachinePassword`

## pseudocode

```c
__int64 __fastcall KerbIumCreateMachinePassword(
        __int64 a1,
        struct _KERB_RPC_HOST_ADDRESS *a2,
        int a3,
        int a4,
        __int64 a5,
        _OWORD *a6,
        struct _KERB_ENCRYPTION_KEY *a7,
        struct _KERB_MESSAGE_BUFFER *a8)
{
  int v8; // edi
  int v9; // esi
  struct _KERB_RPC_HOST_ADDRESS *v10; // r14
  int v11; // ebx
  struct _KERB_MESSAGE_BUFFER *v12; // rbx
  __int64 RandomPassword; // rcx
  USHORT v14; // di
  int v15; // esi
  USHORT v16; // r14
  WCHAR *v17; // rbx
  int v18; // eax
  __int64 v19; // rdx
  __int128 v20; // xmm1
  __int64 v21; // xmm0_8
  char v22; // cl
  struct _UNICODE_STRING v24; // [rsp+48h] [rbp-71h] BYREF
  __int64 v25; // [rsp+58h] [rbp-61h]
  struct _STRING v26; // [rsp+60h] [rbp-59h] BYREF
  __int128 v27; // [rsp+70h] [rbp-49h] BYREF
  __int128 v28; // [rsp+80h] [rbp-39h]
  __int64 v29; // [rsp+90h] [rbp-29h]
  _BYTE v30[8]; // [rsp+98h] [rbp-21h] BYREF
  _BYTE v31[88]; // [rsp+A0h] [rbp-19h] BYREF

  v8 = a4;
  v9 = a3;
  v29 = 0;
  v10 = a2;
  v25 = 0;
  v27 = 0;
  v28 = 0;
  v26 = 0;
  v24 = 0;
  if ( qword_140052C40 == a1 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      WPP_SF_s(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        14,
        WPP_d5c6fd37444639aeca2bc0daa2920ffe_Traceguids,
        "KerbIumCreateMachinePassword");
    if ( v10 )
    {
      if ( v9 )
      {
        if ( a5 )
        {
          *(_OWORD *)a5 = 0;
          if ( a6 )
          {
            *a6 = 0;
            if ( a7 )
            {
              v12 = a8;
              *(_OWORD *)a7 = 0;
              *((_OWORD *)a7 + 1) = 0;
              *((_QWORD *)a7 + 4) = 0;
              if ( a8 )
              {
                *(_OWORD *)a8 = 0;
                RandomPassword = KerberosCryptoPolicy::GenerateRandomPassword(v31);
                if ( *(_BYTE *)(RandomPassword + 16) )
                {
                  if ( (_BYTE)v25 )
                  {
                    if ( &v24 != (struct _UNICODE_STRING *)RandomPassword )
                    {
                      v14 = *(_WORD *)RandomPassword;
                      v15 = *(_DWORD *)(RandomPassword + 2);
                      v16 = *(_WORD *)(RandomPassword + 6);
                      v17 = *(WCHAR **)(RandomPassword + 8);
                      *(_OWORD *)RandomPassword = 0;
                      wil::last_error_context::last_error_context((wil::last_error_context *)v30);
                      KerbFreeString(&v24);
                      wil::last_error_context::~last_error_context((wil::last_error_context *)v30);
                      v24.Length = v14;
                      v8 = a4;
                      *(_DWORD *)&v24.MaximumLength = v15;
                      v9 = a3;
                      *(&v24.MaximumLength + 2) = v16;
                      v10 = a2;
                      v24.Buffer = v17;
                      v12 = a8;
                    }
                  }
                  else
                  {
                    v24 = *(struct _UNICODE_STRING *)RandomPassword;
                    *(_OWORD *)RandomPassword = 0;
                    LOBYTE(v25) = 1;
                  }
                }
                else if ( (_BYTE)v25 )
                {
                  KerbFreeString(&v24);
                  LOBYTE(v25) = 0;
                }
                utl::_OptionalData1<wil::unique_struct<_UNICODE_STRING,void (_UNICODE_STRING *),&void KerbFreeString(_UNICODE_STRING *),std::nullptr_t,0>,0>::~_OptionalData1<wil::unique_struct<_UNICODE_STRING,void (_UNICODE_STRING *),&void KerbFreeString(_UNICODE_STRING *),std::nullptr_t,0>,0>(v31);
                if ( (_BYTE)v25 )
                {
                  v18 = KerbUnicodeStringToKerbString(&v26, &v24);
                  if ( v18 )
                  {
                    v11 = KerbMapKerbError(v18);
                  }
                  else
                  {
                    v11 = KerbClientBuildKerbPriv(
                            v10,
                            v9,
                            (unsigned __int8 *)v26.Buffer,
                            v26.Length,
                            0,
                            v12,
                            (struct _KERB_ENCRYPTION_KEY *)&v27);
                    if ( v11 >= 0 )
                    {
                      if ( v8 )
                      {
                        v11 = EncryptKeyWithMetadata(0x20u, (const struct _KERB_ENCRYPTION_KEY *)&v27, a7);
                        if ( v11 < 0 )
                          goto LABEL_48;
                        if ( !(_BYTE)v25 )
                          __int2c();
                        LOBYTE(v19) = 1;
                        v11 = KerbIumEncryptPassword(a1, v19, &v24, a6);
                        if ( v11 < 0 || v8 == 2 )
                          goto LABEL_48;
                      }
                      else
                      {
                        v20 = v28;
                        *(_OWORD *)a7 = v27;
                        v21 = v29;
                        *((_OWORD *)a7 + 1) = v20;
                        v29 = 0;
                        *((_QWORD *)a7 + 4) = v21;
                        v27 = 0;
                        v28 = 0;
                      }
                      v22 = v25;
                      if ( !(_BYTE)v25 )
                        __int2c();
                      *(_QWORD *)(a5 + 8) = v24.Buffer;
                      if ( !v22 )
                        __int2c();
                      *(_DWORD *)a5 = v24.Length;
                      if ( !v22 )
                        __int2c();
                      v24 = 0;
                    }
                    else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                           && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
                    {
                      WPP_SF_d(
                        *((_QWORD *)WPP_GLOBAL_Control + 2),
                        15,
                        WPP_d5c6fd37444639aeca2bc0daa2920ffe_Traceguids,
                        (unsigned int)v11);
                    }
                  }
                }
                else
                {
                  v11 = -1073741670;
                }
              }
              else
              {
                v11 = -1073741579;
              }
            }
            else
            {
              v11 = -1073741580;
            }
          }
          else
          {
            v11 = -1073741581;
          }
        }
        else
        {
          v11 = -1073741582;
        }
      }
      else
      {
        v11 = -1073741584;
      }
    }
    else
    {
      v11 = -1073741585;
    }
LABEL_48:
    KerbFreeString(&v26);
    KerbFreeKey(&v27);
    goto LABEL_49;
  }
  Sleep(5u);
  v11 = -1073741790;
LABEL_49:
  utl::_OptionalData1<wil::unique_struct<_UNICODE_STRING,void (_UNICODE_STRING *),&void KerbFreeString(_UNICODE_STRING *),std::nullptr_t,0>,0>::~_OptionalData1<wil::unique_struct<_UNICODE_STRING,void (_UNICODE_STRING *),&void KerbFreeString(_UNICODE_STRING *),std::nullptr_t,0>,0>(&v24);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x1400170e0  mov     rax, rsp
0x1400170e3  mov     [rax+20h], r9d
0x1400170e7  mov     [rax+18h], r8d
0x1400170eb  mov     [rax+10h], rdx
0x1400170ef  mov     [rax+8], rcx
0x1400170f3  push    rbp
0x1400170f4  push    rbx
0x1400170f5  push    rsi
0x1400170f6  push    rdi
0x1400170f7  push    r12
0x1400170f9  push    r13
0x1400170fb  push    r14
0x1400170fd  push    r15
0x1400170ff  lea     rbp, [rax-47h]
0x140017103  sub     rsp, 0B8h
0x14001710a  xorps   xmm0, xmm0
0x14001710d  mov     rax, rcx
0x140017110  xor     ecx, ecx
0x140017112  xorps   xmm1, xmm1
0x140017115  cmp     cs:qword_140052C40, rax
0x14001711c  mov     edi, r9d
0x14001711f  mov     esi, r8d
0x140017122  mov     [rbp+3Fh+var_68], rcx
0x140017126  mov     r14, rdx
0x140017129  mov     [rbp+3Fh+var_A0], rcx
0x14001712d  movups  [rbp+3Fh+var_88], xmm0
0x140017131  movups  [rbp+3Fh+var_78], xmm0
0x140017135  movups  xmmword ptr [rbp+3Fh+var_98.Length], xmm0
0x140017139  movups  xmmword ptr [rbp+3Fh+var_B0.Length], xmm1
0x14001713d  jz      short loc_140017154
0x14001713f  mov     ecx, 5; dwMilliseconds
0x140017144  call    cs:__imp_Sleep
0x14001714a  mov     ebx, 0C0000022h
0x14001714f  jmp     loc_14001742A
0x140017154  mov     rcx, cs:WPP_GLOBAL_Control
0x14001715b  lea     rax, WPP_GLOBAL_Control
0x140017162  cmp     rcx, rax
0x140017165  jz      short loc_140017189
0x140017167  test    byte ptr [rcx+1Ch], 4
0x14001716b  jz      short loc_140017189
0x14001716d  mov     rcx, [rcx+10h]
0x140017171  lea     r9, aKerbiumcreatem; "KerbIumCreateMachinePassword"
0x140017178  mov     edx, 0Eh
0x14001717d  lea     r8, WPP_d5c6fd37444639aeca2bc0daa2920ffe_Traceguids
0x140017184  call    WPP_SF_s
0x140017189  test    r14, r14
0x14001718c  jnz     short loc_140017198
0x14001718e  mov     ebx, 0C00000EFh
0x140017193  jmp     loc_140017418
0x140017198  test    esi, esi
0x14001719a  jnz     short loc_1400171A6
0x14001719c  mov     ebx, 0C00000F0h
0x1400171a1  jmp     loc_140017418
0x1400171a6  mov     r12, [rbp+3Fh+arg_20]
0x1400171aa  test    r12, r12
0x1400171ad  jnz     short loc_1400171B9
0x1400171af  mov     ebx, 0C00000F2h
0x1400171b4  jmp     loc_140017418
0x1400171b9  mov     r13, [rbp+3Fh+arg_28]
0x1400171bd  xorps   xmm0, xmm0
0x1400171c0  movdqu  xmmword ptr [r12], xmm0
0x1400171c6  test    r13, r13
0x1400171c9  jnz     short loc_1400171D5
0x1400171cb  mov     ebx, 0C00000F3h
0x1400171d0  jmp     loc_140017418
0x1400171d5  mov     r15, [rbp+3Fh+arg_30]
0x1400171d9  movdqu  xmmword ptr [r13+0], xmm0
0x1400171df  test    r15, r15
0x1400171e2  jnz     short loc_1400171EE
0x1400171e4  mov     ebx, 0C00000F4h
0x1400171e9  jmp     loc_140017418
0x1400171ee  mov     rbx, [rbp+3Fh+arg_38]
0x1400171f5  xor     eax, eax
0x1400171f7  movups  xmmword ptr [r15], xmm0
0x1400171fb  movups  xmmword ptr [r15+10h], xmm0
0x140017200  mov     [r15+20h], rax
0x140017204  test    rbx, rbx
0x140017207  jnz     short loc_140017213
0x140017209  mov     ebx, 0C00000F5h
0x14001720e  jmp     loc_140017418
0x140017213  xorps   xmm0, xmm0
0x140017216  lea     rcx, [rbp+3Fh+var_58]
0x14001721a  movdqu  xmmword ptr [rbx], xmm0
0x14001721e  call    ?GenerateRandomPassword@KerberosCryptoPolicy@@SA?AV?$optional@V?$unique_struct@U_UNICODE_STRING@@$$A6AXPEAU1@@Z$1?KerbFreeString@@YAX0@Z$$T$0A@@wil@@@utl@@_K@Z; KerberosCryptoPolicy::GenerateRandomPassword(unsigned __int64)
0x140017223  mov     rcx, rax
0x140017226  xor     eax, eax
0x140017228  cmp     [rcx+10h], al
0x14001722b  jz      loc_1400172BF
0x140017231  cmp     byte ptr [rbp+3Fh+var_A0], al
0x140017234  jz      short loc_140017296
0x140017236  lea     rax, [rbp+3Fh+var_B0]
0x14001723a  cmp     rax, rcx
0x14001723d  jz      loc_1400172D1
0x140017243  movzx   edi, word ptr [rcx]
0x140017246  xorps   xmm0, xmm0
0x140017249  mov     esi, [rcx+2]
0x14001724c  movzx   r14d, word ptr [rcx+6]
0x140017251  mov     rbx, [rcx+8]
0x140017255  movups  xmmword ptr [rcx], xmm0
0x140017258  lea     rcx, [rbp+3Fh+var_60]; this
0x14001725c  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x140017261  lea     rcx, [rbp+3Fh+var_B0]
0x140017265  call    KerbFreeString
0x14001726a  lea     rcx, [rbp+3Fh+var_60]; this
0x14001726e  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x140017273  mov     [rbp+3Fh+var_B0.Length], di
0x140017277  mov     edi, [rbp+3Fh+arg_18]
0x14001727a  mov     dword ptr [rbp+3Fh+var_B0.MaximumLength], esi
0x14001727d  mov     esi, [rbp+3Fh+arg_10]
0x140017280  mov     word ptr [rbp+3Fh+var_B0+6], r14w
0x140017285  mov     r14, [rbp+3Fh+arg_8]
0x140017289  mov     [rbp+3Fh+var_B0.Buffer], rbx
0x14001728d  mov     rbx, [rbp+3Fh+arg_38]
0x140017294  jmp     short loc_1400172D1
0x140017296  movzx   eax, word ptr [rcx]
0x140017299  xorps   xmm0, xmm0
0x14001729c  mov     [rbp+3Fh+var_B0.Length], ax
0x1400172a0  mov     eax, [rcx+2]
0x1400172a3  mov     dword ptr [rbp+3Fh+var_B0.MaximumLength], eax
0x1400172a6  movzx   eax, word ptr [rcx+6]
0x1400172aa  mov     word ptr [rbp+3Fh+var_B0+6], ax
0x1400172ae  mov     rax, [rcx+8]
0x1400172b2  mov     [rbp+3Fh+var_B0.Buffer], rax
0x1400172b6  movups  xmmword ptr [rcx], xmm0
0x1400172b9  mov     byte ptr [rbp+3Fh+var_A0], 1
0x1400172bd  jmp     short loc_1400172D1
0x1400172bf  cmp     byte ptr [rbp+3Fh+var_A0], al
0x1400172c2  jz      short loc_1400172D1
0x1400172c4  lea     rcx, [rbp+3Fh+var_B0]
0x1400172c8  call    KerbFreeString
0x1400172cd  mov     byte ptr [rbp+3Fh+var_A0], 0
0x1400172d1  lea     rcx, [rbp+3Fh+var_58]
0x1400172d5  call    ??1?$_OptionalData1@V?$unique_struct@U_UNICODE_STRING@@$$A6AXPEAU1@@Z$1?KerbFreeString@@YAX0@Z$$T$0A@@wil@@$0A@@utl@@QEAA@XZ; utl::_OptionalData1<wil::unique_struct<_UNICODE_STRING,void (_UNICODE_STRING *),&KerbFreeString(_UNICODE_STRING *),std::nullptr_t,0>,0>::~_OptionalData1<wil::unique_struct<_UNICODE_STRING,void (_UNICODE_STRING *),&KerbFreeString(_UNICODE_STRING *),std::nullptr_t,0>,0>(void)
0x1400172da  cmp     byte ptr [rbp+3Fh+var_A0], 0
0x1400172de  jnz     short loc_1400172EA
0x1400172e0  mov     ebx, 0C000009Ah
0x1400172e5  jmp     loc_140017418
0x1400172ea  lea     rdx, [rbp+3Fh+var_B0]; struct _UNICODE_STRING *
0x1400172ee  lea     rcx, [rbp+3Fh+var_98]; struct _STRING *
0x1400172f2  call    ?KerbUnicodeStringToKerbString@@YAJPEAU_STRING@@PEAU_UNICODE_STRING@@@Z; KerbUnicodeStringToKerbString(_STRING *,_UNICODE_STRING *)
0x1400172f7  test    eax, eax
0x1400172f9  jz      short loc_140017309
0x1400172fb  mov     ecx, eax; int
0x1400172fd  call    ?KerbMapKerbError@@YAJJ@Z; KerbMapKerbError(long)
0x140017302  mov     ebx, eax
0x140017304  jmp     loc_140017418
0x140017309  movzx   r9d, [rbp+3Fh+var_98.Length]
0x14001730e  lea     rax, [rbp+3Fh+var_88]
0x140017312  mov     r8, [rbp+3Fh+var_98.Buffer]
0x140017316  mov     edx, esi
0x140017318  mov     [rsp+30h], rax
0x14001731d  mov     rcx, r14
0x140017320  mov     [rsp+0F0h+var_C8], rbx
0x140017325  mov     [rsp+0F0h+var_D0], 0
0x14001732e  call    cs:__imp_?KerbClientBuildKerbPriv@@YAJPEAU_KERB_RPC_HOST_ADDRESS@@JPEAEKPEAKPEAU_KERB_MESSAGE_BUFFER@@PEAU_KERB_ENCRYPTION_KEY@@@Z; KerbClientBuildKerbPriv(_KERB_RPC_HOST_ADDRESS *,long,uchar *,ulong,ulong *,_KERB_MESSAGE_BUFFER *,_KERB_ENCRYPTION_KEY *)
0x140017334  mov     ebx, eax
0x140017336  test    eax, eax
0x140017338  jns     short loc_140017378
0x14001733a  mov     rcx, cs:WPP_GLOBAL_Control
0x140017341  lea     rax, WPP_GLOBAL_Control
0x140017348  cmp     rcx, rax
0x14001734b  jz      loc_140017418
0x140017351  test    byte ptr [rcx+1Ch], 1
0x140017355  jz      loc_140017418
0x14001735b  mov     rcx, [rcx+10h]
0x14001735f  lea     r8, WPP_d5c6fd37444639aeca2bc0daa2920ffe_Traceguids
0x140017366  mov     edx, 0Fh
0x14001736b  mov     r9d, ebx
0x14001736e  call    WPP_SF_d
0x140017373  jmp     loc_140017418
0x140017378  test    edi, edi
0x14001737a  jz      short loc_1400173BE
0x14001737c  mov     r8, r15; struct _KERB_ENCRYPTION_KEY *
0x14001737f  lea     rdx, [rbp+3Fh+var_88]; struct _KERB_ENCRYPTION_KEY *
0x140017383  mov     ecx, 20h ; ' '; unsigned int
0x140017388  call    ?EncryptKeyWithMetadata@@YAJKPEBU_KERB_ENCRYPTION_KEY@@PEAU1@@Z; EncryptKeyWithMetadata(ulong,_KERB_ENCRYPTION_KEY const *,_KERB_ENCRYPTION_KEY *)
0x14001738d  mov     ebx, eax
0x14001738f  test    eax, eax
0x140017391  js      loc_140017418
0x140017397  cmp     byte ptr [rbp+3Fh+var_A0], 0
0x14001739b  jnz     short loc_14001739F
0x14001739d  int     2Ch; Windows NT - assertion failure
0x14001739f  mov     rcx, [rbp+3Fh+arg_0]
0x1400173a3  lea     r8, [rbp+3Fh+var_B0]
0x1400173a7  mov     r9, r13
0x1400173aa  mov     dl, 1
0x1400173ac  call    KerbIumEncryptPassword
0x1400173b1  mov     ebx, eax
0x1400173b3  test    eax, eax
0x1400173b5  js      short loc_140017418
0x1400173b7  cmp     edi, 2
0x1400173ba  jz      short loc_140017418
0x1400173bc  jmp     short loc_1400173EB
0x1400173be  movups  xmm0, [rbp+3Fh+var_88]
0x1400173c2  xor     eax, eax
0x1400173c4  movups  xmm1, [rbp+3Fh+var_78]
0x1400173c8  movups  xmmword ptr [r15], xmm0
0x1400173cc  movsd   xmm0, [rbp+3Fh+var_68]
0x1400173d1  movups  xmmword ptr [r15+10h], xmm1
0x1400173d6  mov     [rbp+3Fh+var_68], rax
0x1400173da  xorps   xmm1, xmm1
0x1400173dd  movsd   qword ptr [r15+20h], xmm0
0x1400173e3  movups  [rbp+3Fh+var_88], xmm1
0x1400173e7  movups  [rbp+3Fh+var_78], xmm1
0x1400173eb  mov     cl, byte ptr [rbp+3Fh+var_A0]
0x1400173ee  test    cl, cl
0x1400173f0  jnz     short loc_1400173F4
0x1400173f2  int     2Ch; Windows NT - assertion failure
0x1400173f4  mov     rax, [rbp+3Fh+var_B0.Buffer]
0x1400173f8  mov     [r12+8], rax
0x1400173fd  test    cl, cl
0x1400173ff  jnz     short loc_140017403
0x140017401  int     2Ch; Windows NT - assertion failure
0x140017403  movzx   eax, [rbp+3Fh+var_B0.Length]
0x140017407  mov     [r12], eax
0x14001740b  test    cl, cl
0x14001740d  jnz     short loc_140017411
0x14001740f  int     2Ch; Windows NT - assertion failure
0x140017411  xorps   xmm0, xmm0
0x140017414  movups  xmmword ptr [rbp+3Fh+var_B0.Length], xmm0
0x140017418  lea     rcx, [rbp+3Fh+var_98]
0x14001741c  call    KerbFreeString
0x140017421  lea     rcx, [rbp+3Fh+var_88]
0x140017425  call    KerbFreeKey
0x14001742a  lea     rcx, [rbp+3Fh+var_B0]
0x14001742e  call    ??1?$_OptionalData1@V?$unique_struct@U_UNICODE_STRING@@$$A6AXPEAU1@@Z$1?KerbFreeString@@YAX0@Z$$T$0A@@wil@@$0A@@utl@@QEAA@XZ; utl::_OptionalData1<wil::unique_struct<_UNICODE_STRING,void (_UNICODE_STRING *),&KerbFreeString(_UNICODE_STRING *),std::nullptr_t,0>,0>::~_OptionalData1<wil::unique_struct<_UNICODE_STRING,void (_UNICODE_STRING *),&KerbFreeString(_UNICODE_STRING *),std::nullptr_t,0>,0>(void)
0x140017433  mov     eax, ebx
0x140017435  add     rsp, 0B8h
0x14001743c  pop     r15
0x14001743e  pop     r14
0x140017440  pop     r13
0x140017442  pop     r12
0x140017444  pop     rdi
0x140017445  pop     rsi
0x140017446  pop     rbx
0x140017447  pop     rbp
0x140017448  retn
```
