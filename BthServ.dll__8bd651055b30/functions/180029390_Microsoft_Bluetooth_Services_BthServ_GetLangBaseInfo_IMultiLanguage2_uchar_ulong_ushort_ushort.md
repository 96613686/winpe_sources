# Microsoft::Bluetooth::Services::BthServ::GetLangBaseInfo(IMultiLanguage2 *,uchar *,ulong,ushort *,ushort *)

- ea: `0x180029390`
- end: `0x180029639`
- name: `?GetLangBaseInfo@BthServ@Services@Bluetooth@Microsoft@@YAKPEAUIMultiLanguage2@@PEAEKPEAG2@Z`
- size: `681`
- prototype: `unsigned int(Microsoft::Bluetooth::Services::BthServ *__hidden this, struct IMultiLanguage2 *, unsigned __int8 *, unsigned int, unsigned __int16 *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x180029084`

## callees

- `0x180001790`
- `0x180028c44`
- `0x180028d24`
- `0x180029390`
- `0x180034300`
- `0x180034d20`
- `0x180037010`

## import_xrefs

- `api-ms-win-core-localization-l1-2-0!GetThreadLocale` at `0x18002945c`
- `api-ms-win-core-localization-l1-2-0!GetThreadLocale` at `0x18002945c`
- `OLEAUT32!__imp_SysAllocString` at `0x1800294dc`
- `OLEAUT32!__imp_SysAllocString` at `0x1800294dc`
- `OLEAUT32!__imp_SysFreeString` at `0x18002951c`
- `OLEAUT32!__imp_SysFreeString` at `0x18002951c`

## pseudocode

```c
unsigned int __fastcall Microsoft::Bluetooth::Services::BthServ::GetLangBaseInfo(
        Microsoft::Bluetooth::Services::BthServ *this,
        struct IMultiLanguage2 *a2,
        unsigned __int8 *a3,
        _WORD *a4,
        unsigned __int16 *a5)
{
  Microsoft::Bluetooth::Services::BthServ *v5; // r14
  unsigned int v7; // edi
  unsigned __int8 *v8; // rsi
  __int16 v9; // r15
  unsigned __int16 v10; // bx
  BSTR v11; // rax
  int v12; // ebx
  __int16 v13; // r14
  unsigned int result; // eax
  Microsoft::Bluetooth::Services::BthServ *v15; // rbx
  unsigned int v16; // edi
  __int16 v17; // si
  struct _SDP_ELEMENT_DATA *v18; // [rsp+20h] [rbp-61h]
  struct _SDP_ELEMENT_DATA *v19; // [rsp+20h] [rbp-61h]
  struct _SDP_ELEMENT_DATA *v20; // [rsp+20h] [rbp-61h]
  struct _SDP_ELEMENT_DATA *v21; // [rsp+20h] [rbp-61h]
  struct _SDP_ELEMENT_DATA *v22; // [rsp+20h] [rbp-61h]
  struct _SDP_ELEMENT_DATA *v23; // [rsp+20h] [rbp-61h]
  struct _SDP_ELEMENT_DATA *v24; // [rsp+20h] [rbp-61h]
  struct _SDP_ELEMENT_DATA *v25; // [rsp+20h] [rbp-61h]
  struct _SDP_ELEMENT_DATA *v26; // [rsp+20h] [rbp-61h]
  __int16 v27; // [rsp+30h] [rbp-51h]
  unsigned int v28[2]; // [rsp+38h] [rbp-49h] BYREF
  Microsoft::Bluetooth::Services::BthServ *v29[2]; // [rsp+40h] [rbp-41h] BYREF
  unsigned __int8 *v30; // [rsp+50h] [rbp-31h]
  int v31; // [rsp+58h] [rbp-29h] BYREF
  _DWORD v32[3]; // [rsp+5Ch] [rbp-25h]
  Microsoft::Bluetooth::Services::BthServ *v33; // [rsp+68h] [rbp-19h]
  Microsoft::Bluetooth::Services::BthServ *v34; // [rsp+70h] [rbp-11h]
  OLECHAR psz[4]; // [rsp+78h] [rbp-9h] BYREF

  v5 = this;
  v33 = this;
  v32[0] = (_DWORD)a3;
  v34 = (Microsoft::Bluetooth::Services::BthServ *)a2;
  v30 = 0;
  *(_OWORD *)v29 = 0;
  if ( Microsoft::Bluetooth::Services::BthServ::BluetoothSdpGetAttributeValue(
         (Microsoft::Bluetooth::Services::BthServ *)a2,
         (unsigned __int8 *)(unsigned int)a3,
         6u,
         (unsigned __int16)v29,
         v18) )
  {
    return 0;
  }
  if ( LODWORD(v29[0]) != 6 )
    return 87;
  v7 = (unsigned int)v30;
  v8 = (unsigned __int8 *)v29[1];
  if ( (int)SdpValidateStream(v29[1], (_DWORD)v30, 0, 0, 0) < 0 || (int)SdpVerifyServiceRecord(v8) < 0 )
    return 87;
  v31 = 0;
  *(_QWORD *)v28 = 0;
  v9 = GetThreadLocale() & 0x3FF;
  if ( Microsoft::Bluetooth::Services::BthServ::BluetoothSdpGetContainerElementData(
         (Microsoft::Bluetooth::Services::BthServ *)v8,
         (unsigned __int8 *)v7,
         (unsigned int)v28,
         (void **)v29,
         v19) == 259 )
  {
LABEL_15:
    Microsoft::Bluetooth::Services::BthServ::BluetoothSdpGetAttributeValue(
      v34,
      (unsigned __int8 *)v32[0],
      6u,
      (unsigned __int16)v29,
      v20);
    v15 = v29[1];
    v16 = (unsigned int)v30;
    *(_QWORD *)v28 = 0;
    result = Microsoft::Bluetooth::Services::BthServ::BluetoothSdpGetContainerElementData(
               v29[1],
               (unsigned __int8 *)(unsigned int)v30,
               (unsigned int)v28,
               (void **)v29,
               v23);
    if ( result != 259 )
    {
      while ( !result )
      {
        Microsoft::Bluetooth::Services::BthServ::BluetoothSdpGetContainerElementData(
          v15,
          (unsigned __int8 *)v16,
          (unsigned int)v28,
          (void **)v29,
          v24);
        v17 = (__int16)v29[1];
        Microsoft::Bluetooth::Services::BthServ::BluetoothSdpGetContainerElementData(
          v15,
          (unsigned __int8 *)v16,
          (unsigned int)v28,
          (void **)v29,
          v25);
        if ( LOWORD(v29[1]) == 256 )
        {
          *a4 = v17;
          *a5 = 256;
          return 0;
        }
        result = Microsoft::Bluetooth::Services::BthServ::BluetoothSdpGetContainerElementData(
                   v15,
                   (unsigned __int8 *)v16,
                   (unsigned int)v28,
                   (void **)v29,
                   v26);
        if ( result == 259 )
          return 0;
      }
      return result;
    }
    return 0;
  }
  while ( 1 )
  {
    v10 = (unsigned __int16)v29[1];
    Microsoft::Bluetooth::Services::BthServ::BluetoothSdpGetContainerElementData(
      (Microsoft::Bluetooth::Services::BthServ *)v8,
      (unsigned __int8 *)v7,
      (unsigned int)v28,
      (void **)v29,
      v20);
    v27 = (__int16)v29[1];
    Microsoft::Bluetooth::Services::BthServ::BluetoothSdpGetContainerElementData(
      (Microsoft::Bluetooth::Services::BthServ *)v8,
      (unsigned __int8 *)v7,
      (unsigned int)v28,
      (void **)v29,
      v21);
    psz[0] = HIBYTE(v10);
    psz[2] = 0;
    psz[1] = (unsigned __int8)v10;
    v11 = SysAllocString(psz);
    *(_QWORD *)&v32[1] = v11;
    if ( !v11 )
      return 1450;
    v12 = (*(__int64 (__fastcall **)(Microsoft::Bluetooth::Services::BthServ *, int *, BSTR))(*(_QWORD *)v5 + 112LL))(
            v5,
            &v31,
            v11);
    v13 = v31 & 0x3FF;
    SysFreeString(*(BSTR *)&v32[1]);
    if ( v12 >= 0 && v13 == v9 )
    {
      *a4 = v27;
      *a5 = (unsigned __int16)v29[1];
      return 0;
    }
    if ( Microsoft::Bluetooth::Services::BthServ::BluetoothSdpGetContainerElementData(
           (Microsoft::Bluetooth::Services::BthServ *)v8,
           (unsigned __int8 *)v7,
           (unsigned int)v28,
           (void **)v29,
           v22) == 259 )
      goto LABEL_15;
    v5 = v33;
  }
}

```

## disassembly

```asm
0x180029390  push    rbp
0x180029392  push    rbx
0x180029393  push    rsi
0x180029394  push    rdi
0x180029395  push    r12
0x180029397  push    r13
0x180029399  push    r14
0x18002939b  push    r15
0x18002939d  lea     rbp, [rsp-17h]
0x1800293a2  sub     rsp, 98h
0x1800293a9  mov     rax, cs:__security_cookie
0x1800293b0  xor     rax, rsp
0x1800293b3  mov     [rbp+4Fh+var_50], rax
0x1800293b7  mov     r13, [rbp+4Fh+arg_20]
0x1800293bb  mov     r14, rcx
0x1800293be  mov     [rbp+4Fh+var_68], rcx
0x1800293c2  mov     r10d, r8d
0x1800293c5  xor     ecx, ecx
0x1800293c7  mov     dword ptr [rbp+4Fh+var_74], r8d
0x1800293cb  mov     rax, rdx
0x1800293ce  mov     [rbp+4Fh+var_60], rdx
0x1800293d2  mov     r12, r9
0x1800293d5  mov     [rbp+4Fh+var_80], rcx
0x1800293d9  xorps   xmm0, xmm0
0x1800293dc  lea     r9, [rbp+4Fh+var_90]; unsigned __int16
0x1800293e0  lea     ebx, [rcx+6]
0x1800293e3  mov     edx, r10d; unsigned __int8 *
0x1800293e6  mov     r8d, ebx; unsigned int
0x1800293e9  mov     rcx, rax; this
0x1800293ec  movups  xmmword ptr [rbp+4Fh+var_90], xmm0
0x1800293f0  call    ?BluetoothSdpGetAttributeValue@BthServ@Services@Bluetooth@Microsoft@@YAKPEAEKGPEAU_SDP_ELEMENT_DATA@@@Z; Microsoft::Bluetooth::Services::BthServ::BluetoothSdpGetAttributeValue(uchar *,ulong,ushort,_SDP_ELEMENT_DATA *)
0x1800293f5  test    eax, eax
0x1800293f7  jnz     loc_180029560
0x1800293fd  cmp     dword ptr [rbp+4Fh+var_90], ebx
0x180029400  jnz     loc_18002962F
0x180029406  mov     rdi, [rbp+4Fh+var_80]
0x18002940a  xor     r9d, r9d
0x18002940d  mov     rsi, [rbp+4Fh+var_90+8]
0x180029411  mov     edx, edi
0x180029413  mov     rcx, rsi
0x180029416  mov     [rsp+0D0h+var_B0], 0; struct _SDP_ELEMENT_DATA *
0x18002941f  xor     r8d, r8d
0x180029422  call    SdpValidateStream
0x180029427  test    eax, eax
0x180029429  js      loc_18002962F
0x18002942f  lea     r9, [rbp+4Fh+var_A0]
0x180029433  mov     [rbp+4Fh+var_A0], bx
0x180029437  lea     r8d, [rbx+2]
0x18002943b  mov     edx, edi
0x18002943d  mov     rcx, rsi; unsigned __int8 *
0x180029440  call    SdpVerifyServiceRecord
0x180029445  test    eax, eax
0x180029447  js      loc_18002962F
0x18002944d  mov     [rbp+4Fh+var_78], 0
0x180029454  mov     qword ptr [rbp+4Fh+var_98], 0
0x18002945c  call    cs:__imp_GetThreadLocale
0x180029462  lea     r9, [rbp+4Fh+var_90]; void **
0x180029466  mov     edx, edi; unsigned __int8 *
0x180029468  mov     r15d, eax
0x18002946b  lea     r8, [rbp+4Fh+var_98]; unsigned int
0x18002946f  mov     eax, 3FFh
0x180029474  mov     rcx, rsi; this
0x180029477  and     r15w, ax
0x18002947b  call    ?BluetoothSdpGetContainerElementData@BthServ@Services@Bluetooth@Microsoft@@YAKPEAEKPEAPEAXPEAU_SDP_ELEMENT_DATA@@@Z; Microsoft::Bluetooth::Services::BthServ::BluetoothSdpGetContainerElementData(uchar *,ulong,void * *,_SDP_ELEMENT_DATA *)
0x180029480  cmp     eax, 103h
0x180029485  jz      loc_18002958E
0x18002948b  movzx   ebx, word ptr [rbp+4Fh+var_90+8]
0x18002948f  lea     r9, [rbp+4Fh+var_90]; void **
0x180029493  lea     r8, [rbp+4Fh+var_98]; unsigned int
0x180029497  mov     edx, edi; unsigned __int8 *
0x180029499  mov     rcx, rsi; this
0x18002949c  call    ?BluetoothSdpGetContainerElementData@BthServ@Services@Bluetooth@Microsoft@@YAKPEAEKPEAPEAXPEAU_SDP_ELEMENT_DATA@@@Z; Microsoft::Bluetooth::Services::BthServ::BluetoothSdpGetContainerElementData(uchar *,ulong,void * *,_SDP_ELEMENT_DATA *)
0x1800294a1  movzx   eax, word ptr [rbp+4Fh+var_90+8]
0x1800294a5  lea     r9, [rbp+4Fh+var_90]; void **
0x1800294a9  lea     r8, [rbp+4Fh+var_98]; unsigned int
0x1800294ad  mov     [rbp+4Fh+var_A0], ax
0x1800294b1  mov     edx, edi; unsigned __int8 *
0x1800294b3  mov     rcx, rsi; this
0x1800294b6  call    ?BluetoothSdpGetContainerElementData@BthServ@Services@Bluetooth@Microsoft@@YAKPEAEKPEAPEAXPEAU_SDP_ELEMENT_DATA@@@Z; Microsoft::Bluetooth::Services::BthServ::BluetoothSdpGetContainerElementData(uchar *,ulong,void * *,_SDP_ELEMENT_DATA *)
0x1800294bb  movzx   eax, bx
0x1800294be  lea     rcx, [rbp+4Fh+psz]; psz
0x1800294c2  shr     ax, 8
0x1800294c6  mov     [rbp+4Fh+psz], ax
0x1800294ca  mov     eax, 0FFh
0x1800294cf  and     bx, ax
0x1800294d2  xor     eax, eax
0x1800294d4  mov     [rbp+4Fh+var_54], ax
0x1800294d8  mov     [rbp+4Fh+var_56], bx
0x1800294dc  call    cs:__imp_SysAllocString
0x1800294e2  mov     qword ptr [rbp+4Fh+var_74+4], rax
0x1800294e6  mov     rdx, rax
0x1800294e9  test    rax, rax
0x1800294ec  jz      loc_180029582
0x1800294f2  mov     rcx, [r14]
0x1800294f5  mov     r8, rdx
0x1800294f8  lea     rdx, [rbp+4Fh+var_78]
0x1800294fc  mov     rax, [rcx+70h]
0x180029500  mov     rcx, r14
0x180029503  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029508  movzx   r14d, word ptr [rbp+4Fh+var_78]
0x18002950d  mov     ebx, eax
0x18002950f  mov     rcx, qword ptr [rbp+4Fh+var_74+4]; bstrString
0x180029513  mov     eax, 3FFh
0x180029518  and     r14w, ax
0x18002951c  call    cs:__imp_SysFreeString
0x180029522  test    ebx, ebx
0x180029524  js      short loc_18002952C
0x180029526  cmp     r14w, r15w
0x18002952a  jz      short loc_18002954E
0x18002952c  lea     r9, [rbp+4Fh+var_90]; void **
0x180029530  mov     edx, edi; unsigned __int8 *
0x180029532  lea     r8, [rbp+4Fh+var_98]; unsigned int
0x180029536  mov     rcx, rsi; this
0x180029539  call    ?BluetoothSdpGetContainerElementData@BthServ@Services@Bluetooth@Microsoft@@YAKPEAEKPEAPEAXPEAU_SDP_ELEMENT_DATA@@@Z; Microsoft::Bluetooth::Services::BthServ::BluetoothSdpGetContainerElementData(uchar *,ulong,void * *,_SDP_ELEMENT_DATA *)
0x18002953e  cmp     eax, 103h
0x180029543  jz      short loc_180029589
0x180029545  mov     r14, [rbp+4Fh+var_68]
0x180029549  jmp     loc_18002948B
0x18002954e  movzx   eax, [rbp+4Fh+var_A0]
0x180029552  mov     [r12], ax
0x180029557  movzx   eax, word ptr [rbp+4Fh+var_90+8]
0x18002955b  mov     [r13+0], ax
0x180029560  xor     eax, eax
0x180029562  mov     rcx, [rbp+4Fh+var_50]
0x180029566  xor     rcx, rsp; StackCookie
0x180029569  call    __security_check_cookie
0x18002956e  add     rsp, 98h
0x180029575  pop     r15
0x180029577  pop     r14
0x180029579  pop     r13
0x18002957b  pop     r12
0x18002957d  pop     rdi
0x18002957e  pop     rsi
0x18002957f  pop     rbx
0x180029580  pop     rbp
0x180029581  retn
0x180029582  mov     eax, 5AAh
0x180029587  jmp     short loc_180029562
0x180029589  mov     ebx, 6
0x18002958e  mov     edx, dword ptr [rbp+4Fh+var_74]; unsigned __int8 *
0x180029591  lea     r9, [rbp+4Fh+var_90]; unsigned __int16
0x180029595  mov     rcx, [rbp+4Fh+var_60]; this
0x180029599  mov     r8d, ebx; unsigned int
0x18002959c  call    ?BluetoothSdpGetAttributeValue@BthServ@Services@Bluetooth@Microsoft@@YAKPEAEKGPEAU_SDP_ELEMENT_DATA@@@Z; Microsoft::Bluetooth::Services::BthServ::BluetoothSdpGetAttributeValue(uchar *,ulong,ushort,_SDP_ELEMENT_DATA *)
0x1800295a1  mov     rbx, [rbp+4Fh+var_90+8]
0x1800295a5  lea     r9, [rbp+4Fh+var_90]; void **
0x1800295a9  mov     edi, dword ptr [rbp+4Fh+var_80]
0x1800295ac  lea     r8, [rbp+4Fh+var_98]; unsigned int
0x1800295b0  mov     rcx, rbx; this
0x1800295b3  mov     qword ptr [rbp+4Fh+var_98], 0
0x1800295bb  mov     edx, edi; unsigned __int8 *
0x1800295bd  call    ?BluetoothSdpGetContainerElementData@BthServ@Services@Bluetooth@Microsoft@@YAKPEAEKPEAPEAXPEAU_SDP_ELEMENT_DATA@@@Z; Microsoft::Bluetooth::Services::BthServ::BluetoothSdpGetContainerElementData(uchar *,ulong,void * *,_SDP_ELEMENT_DATA *)
0x1800295c2  mov     r15d, 103h
0x1800295c8  cmp     eax, r15d
0x1800295cb  jz      short loc_180029560
0x1800295cd  lea     r14d, [r15-3]
0x1800295d1  test    eax, eax
0x1800295d3  jnz     short loc_180029562
0x1800295d5  lea     r9, [rbp+4Fh+var_90]; void **
0x1800295d9  mov     edx, edi; unsigned __int8 *
0x1800295db  lea     r8, [rbp+4Fh+var_98]; unsigned int
0x1800295df  mov     rcx, rbx; this
0x1800295e2  call    ?BluetoothSdpGetContainerElementData@BthServ@Services@Bluetooth@Microsoft@@YAKPEAEKPEAPEAXPEAU_SDP_ELEMENT_DATA@@@Z; Microsoft::Bluetooth::Services::BthServ::BluetoothSdpGetContainerElementData(uchar *,ulong,void * *,_SDP_ELEMENT_DATA *)
0x1800295e7  movzx   esi, word ptr [rbp+4Fh+var_90+8]
0x1800295eb  lea     r9, [rbp+4Fh+var_90]; void **
0x1800295ef  lea     r8, [rbp+4Fh+var_98]; unsigned int
0x1800295f3  mov     edx, edi; unsigned __int8 *
0x1800295f5  mov     rcx, rbx; this
0x1800295f8  call    ?BluetoothSdpGetContainerElementData@BthServ@Services@Bluetooth@Microsoft@@YAKPEAEKPEAPEAXPEAU_SDP_ELEMENT_DATA@@@Z; Microsoft::Bluetooth::Services::BthServ::BluetoothSdpGetContainerElementData(uchar *,ulong,void * *,_SDP_ELEMENT_DATA *)
0x1800295fd  cmp     r14w, word ptr [rbp+4Fh+var_90+8]
0x180029602  jz      short loc_180029620
0x180029604  lea     r9, [rbp+4Fh+var_90]; void **
0x180029608  mov     edx, edi; unsigned __int8 *
0x18002960a  lea     r8, [rbp+4Fh+var_98]; unsigned int
0x18002960e  mov     rcx, rbx; this
0x180029611  call    ?BluetoothSdpGetContainerElementData@BthServ@Services@Bluetooth@Microsoft@@YAKPEAEKPEAPEAXPEAU_SDP_ELEMENT_DATA@@@Z; Microsoft::Bluetooth::Services::BthServ::BluetoothSdpGetContainerElementData(uchar *,ulong,void * *,_SDP_ELEMENT_DATA *)
0x180029616  cmp     eax, r15d
0x180029619  jnz     short loc_1800295D1
0x18002961b  jmp     loc_180029560
0x180029620  mov     [r12], si
0x180029625  mov     [r13+0], r14w
0x18002962a  jmp     loc_180029560
0x18002962f  mov     eax, 57h ; 'W'
0x180029634  jmp     loc_180029562
```
