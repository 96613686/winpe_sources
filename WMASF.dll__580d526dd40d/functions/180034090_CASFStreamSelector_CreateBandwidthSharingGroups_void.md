# CASFStreamSelector::CreateBandwidthSharingGroups(void)

- ea: `0x180034090`
- end: `0x180034316`
- name: `?CreateBandwidthSharingGroups@CASFStreamSelector@@IEAAJXZ`
- size: `646`
- prototype: `__int64 __fastcall(CASFStreamSelector *__hidden this)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180039510`

## callees

- `0x180001174`
- `0x1800015d0`
- `0x180031360`
- `0x180033438`
- `0x180033a40`
- `0x180033d38`
- `0x180033da0`
- `0x180034090`
- `0x180037f08`
- `0x180040010`

## pseudocode

```c
__int64 __fastcall CASFStreamSelector::CreateBandwidthSharingGroups(CASFStreamSelector *this)
{
  __int64 v2; // rcx
  __int64 result; // rax
  int v4; // ebx
  int v5; // ebx
  CASFStreamSelector::STREAM_GROUP *v6; // rax
  __int64 v7; // rax
  CASFStreamSelector::STREAM_GROUP *v8; // rbx
  unsigned __int16 i; // r14
  __int64 v10; // rcx
  struct CASFStreamSelector::STREAM_INFO *v11; // rax
  unsigned int v12; // [rsp+30h] [rbp-40h] BYREF
  __int64 v13; // [rsp+38h] [rbp-38h] BYREF
  __int64 v14; // [rsp+40h] [rbp-30h] BYREF
  __int64 v15; // [rsp+48h] [rbp-28h] BYREF
  __int64 v16; // [rsp+50h] [rbp-20h] BYREF
  _WORD v17[2]; // [rsp+58h] [rbp-18h] BYREF
  unsigned __int16 v18; // [rsp+5Ch] [rbp-14h] BYREF
  int v19; // [rsp+60h] [rbp-10h] BYREF
  int v20; // [rsp+64h] [rbp-Ch] BYREF

  v2 = *((_QWORD *)this + 3);
  v15 = 0;
  result = ASFGetRootObject(v2, &CLSID_ASFHeaderObject, &IID_IASFUnknownContainer, &v15);
  if ( (int)result >= 0 )
  {
    v14 = 0;
    v16 = 0;
    v13 = 0;
    v19 = 0;
    v4 = (*(__int64 (__fastcall **)(__int64, GUID *, __int64 *))(*(_QWORD *)v15 + 72LL))(
           v15,
           &CLSID_ASFBandwidthSharingObject,
           &v14);
    if ( v15 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
      v15 = 0;
    }
    if ( v4 >= 0 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 40LL))(v14);
      while ( !(*(unsigned int (__fastcall **)(__int64, __int64, __int64 *, int *))(*(_QWORD *)v14 + 24LL))(
                 v14,
                 1,
                 &v16,
                 &v19) )
      {
        v5 = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))v16)(v16, &IID_IASFBandwidthSharingObject, &v13);
        if ( v16 )
        {
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
          v16 = 0;
        }
        if ( v5 >= 0 )
        {
          v17[0] = 0;
          (*(void (__fastcall **)(__int64, _WORD *))(*(_QWORD *)v13 + 112LL))(v13, v17);
          if ( v17[0] )
          {
            v6 = (CASFStreamSelector::STREAM_GROUP *)operator new(0xF0u);
            if ( !v6
              || (v7 = CASFStreamSelector::STREAM_GROUP::STREAM_GROUP(v6),
                  (v8 = (CASFStreamSelector::STREAM_GROUP *)v7) == 0) )
            {
              if ( v13 )
              {
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
                v13 = 0;
              }
              if ( v14 )
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
              return 2147942414LL;
            }
            v20 = 0;
            (*(void (__fastcall **)(__int64, __int64, int *))(*(_QWORD *)v13 + 96LL))(v13, v7 + 236, &v20);
            for ( i = 0; i < v17[0]; ++i )
            {
              v18 = 0;
              v12 = 0;
              (*(void (__fastcall **)(__int64, _QWORD, unsigned __int16 *))(*(_QWORD *)v13 + 120LL))(v13, i, &v18);
              CASFStreamSelector::GetStreamInfo(v10, (char *)this + 64, v18, &v12);
              v11 = (struct CASFStreamSelector::STREAM_INFO *)CTDynArray<CASFStreamSelector::STREAM_INFO *,20>::operator[](
                                                                (char *)this + 64,
                                                                v12);
              CASFStreamSelector::STREAM_GROUP::Add(v8, v11);
            }
            CTDynArray<CASFStreamSelector::STREAM_GROUP *,20>::Add((char *)this + 512, v8);
          }
        }
        if ( v13 )
        {
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
          v13 = 0;
        }
      }
      if ( v14 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
      return 0;
    }
    else
    {
      return (unsigned int)v4;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180034090  mov     [rsp-28h+arg_8], rbx
0x180034095  mov     [rsp-28h+arg_10], rsi
0x18003409a  push    rbp
0x18003409b  push    rdi
0x18003409c  push    r12
0x18003409e  push    r14
0x1800340a0  push    r15
0x1800340a2  mov     rbp, rsp
0x1800340a5  sub     rsp, 70h
0x1800340a9  mov     rax, cs:__security_cookie
0x1800340b0  xor     rax, rsp
0x1800340b3  mov     [rbp+var_8], rax
0x1800340b7  mov     rdi, rcx
0x1800340ba  lea     r9, [rbp+var_28]
0x1800340be  mov     rcx, [rcx+18h]
0x1800340c2  lea     r8, IID_IASFUnknownContainer
0x1800340c9  xor     r15d, r15d
0x1800340cc  lea     rdx, CLSID_ASFHeaderObject
0x1800340d3  mov     [rbp+var_28], r15
0x1800340d7  call    ASFGetRootObject
0x1800340dc  test    eax, eax
0x1800340de  js      loc_1800342F1
0x1800340e4  mov     rcx, [rbp+var_28]
0x1800340e8  lea     r8, [rbp+var_30]
0x1800340ec  mov     [rbp+var_30], r15
0x1800340f0  lea     rdx, CLSID_ASFBandwidthSharingObject
0x1800340f7  mov     [rbp+var_20], r15
0x1800340fb  mov     [rbp+var_38], r15
0x1800340ff  mov     [rbp+var_10], r15d
0x180034103  mov     rax, [rcx]
0x180034106  mov     rax, [rax+48h]
0x18003410a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003410f  mov     rcx, [rbp+var_28]
0x180034113  mov     ebx, eax
0x180034115  test    rcx, rcx
0x180034118  jz      short loc_18003412A
0x18003411a  mov     rdx, [rcx]
0x18003411d  mov     rax, [rdx+10h]
0x180034121  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034126  mov     [rbp+var_28], r15
0x18003412a  test    ebx, ebx
0x18003412c  jns     short loc_180034135
0x18003412e  mov     eax, ebx
0x180034130  jmp     loc_1800342F1
0x180034135  mov     rcx, [rbp+var_30]
0x180034139  mov     rax, [rcx]
0x18003413c  mov     rax, [rax+28h]
0x180034140  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034145  mov     r12d, 1
0x18003414b  mov     rcx, [rbp+var_30]
0x18003414f  lea     r9, [rbp+var_10]
0x180034153  lea     r8, [rbp+var_20]
0x180034157  mov     edx, r12d
0x18003415a  mov     rax, [rcx]
0x18003415d  mov     rax, [rax+18h]
0x180034161  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034166  test    eax, eax
0x180034168  jnz     loc_1800342DA
0x18003416e  mov     rcx, [rbp+var_20]
0x180034172  lea     r8, [rbp+var_38]
0x180034176  lea     rdx, IID_IASFBandwidthSharingObject
0x18003417d  mov     rax, [rcx]
0x180034180  mov     rax, [rax]
0x180034183  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034188  mov     rcx, [rbp+var_20]
0x18003418c  mov     ebx, eax
0x18003418e  test    rcx, rcx
0x180034191  jz      short loc_1800341A3
0x180034193  mov     rdx, [rcx]
0x180034196  mov     rax, [rdx+10h]
0x18003419a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003419f  mov     [rbp+var_20], r15
0x1800341a3  test    ebx, ebx
0x1800341a5  js      loc_180034283
0x1800341ab  mov     rcx, [rbp+var_38]
0x1800341af  lea     rdx, [rbp+var_18]
0x1800341b3  mov     [rbp+var_18], r15w
0x1800341b8  mov     rax, [rcx]
0x1800341bb  mov     rax, [rax+70h]
0x1800341bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800341c4  cmp     [rbp+var_18], r15w
0x1800341c9  jz      loc_180034283
0x1800341cf  mov     ecx, 0F0h; Size
0x1800341d4  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800341d9  test    rax, rax
0x1800341dc  jz      loc_1800342A5
0x1800341e2  mov     rcx, rax; this
0x1800341e5  call    ??0STREAM_GROUP@CASFStreamSelector@@QEAA@XZ; CASFStreamSelector::STREAM_GROUP::STREAM_GROUP(void)
0x1800341ea  mov     rbx, rax
0x1800341ed  test    rax, rax
0x1800341f0  jz      loc_1800342A5
0x1800341f6  mov     rcx, [rbp+var_38]
0x1800341fa  lea     rdx, [rbx+0ECh]
0x180034201  mov     [rbp+var_C], r15d
0x180034205  lea     r8, [rbp+var_C]
0x180034209  mov     rax, [rcx]
0x18003420c  mov     rax, [rax+60h]
0x180034210  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034215  mov     r14d, r15d
0x180034218  cmp     r15w, [rbp+var_18]
0x18003421d  jnb     short loc_180034274
0x18003421f  mov     rcx, [rbp+var_38]
0x180034223  lea     r8, [rbp+var_14]
0x180034227  mov     [rbp+var_14], r15w
0x18003422c  movzx   edx, r14w
0x180034230  mov     [rbp+var_40], r15d
0x180034234  mov     rax, [rcx]
0x180034237  mov     rax, [rax+78h]
0x18003423b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034240  movzx   r8d, [rbp+var_14]
0x180034245  lea     r9, [rbp+var_40]
0x180034249  lea     rdx, [rdi+40h]
0x18003424d  call    ?GetStreamInfo@CASFStreamSelector@@IEAAJPEAV?$CTDynArray@PEAUSTREAM_INFO@CASFStreamSelector@@$0BE@@@GPEAK@Z; CASFStreamSelector::GetStreamInfo(CTDynArray<CASFStreamSelector::STREAM_INFO *,20> *,ushort,ulong *)
0x180034252  mov     edx, [rbp+var_40]
0x180034255  lea     rcx, [rdi+40h]
0x180034259  call    ??A?$CTDynArray@PEAUSTREAM_INFO@CASFStreamSelector@@$0BE@@@QEBAPEAUSTREAM_INFO@CASFStreamSelector@@K@Z; CTDynArray<CASFStreamSelector::STREAM_INFO *,20>::operator[](ulong)
0x18003425e  mov     rdx, rax; struct CASFStreamSelector::STREAM_INFO *
0x180034261  mov     rcx, rbx; this
0x180034264  call    ?Add@STREAM_GROUP@CASFStreamSelector@@QEAAXPEAUSTREAM_INFO@2@@Z; CASFStreamSelector::STREAM_GROUP::Add(CASFStreamSelector::STREAM_INFO *)
0x180034269  add     r14w, r12w
0x18003426d  cmp     r14w, [rbp+var_18]
0x180034272  jb      short loc_18003421F
0x180034274  lea     rcx, [rdi+200h]
0x18003427b  mov     rdx, rbx
0x18003427e  call    ?Add@?$CTDynArray@PEAUSTREAM_GROUP@CASFStreamSelector@@$0BE@@@QEAAHPEAUSTREAM_GROUP@CASFStreamSelector@@PEAK@Z; CTDynArray<CASFStreamSelector::STREAM_GROUP *,20>::Add(CASFStreamSelector::STREAM_GROUP *,ulong *)
0x180034283  mov     rcx, [rbp+var_38]
0x180034287  test    rcx, rcx
0x18003428a  jz      loc_18003414B
0x180034290  mov     rax, [rcx]
0x180034293  mov     rax, [rax+10h]
0x180034297  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003429c  mov     [rbp+var_38], r15
0x1800342a0  jmp     loc_18003414B
0x1800342a5  mov     rcx, [rbp+var_38]
0x1800342a9  test    rcx, rcx
0x1800342ac  jz      short loc_1800342BE
0x1800342ae  mov     rax, [rcx]
0x1800342b1  mov     rax, [rax+10h]
0x1800342b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800342ba  mov     [rbp+var_38], r15
0x1800342be  mov     rcx, [rbp+var_30]
0x1800342c2  test    rcx, rcx
0x1800342c5  jz      short loc_1800342D3
0x1800342c7  mov     rax, [rcx]
0x1800342ca  mov     rax, [rax+10h]
0x1800342ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800342d3  mov     eax, 8007000Eh
0x1800342d8  jmp     short loc_1800342F1
0x1800342da  mov     rcx, [rbp+var_30]
0x1800342de  test    rcx, rcx
0x1800342e1  jz      short loc_1800342EF
0x1800342e3  mov     rax, [rcx]
0x1800342e6  mov     rax, [rax+10h]
0x1800342ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800342ef  xor     eax, eax
0x1800342f1  mov     rcx, [rbp+var_8]
0x1800342f5  xor     rcx, rsp; StackCookie
0x1800342f8  call    __security_check_cookie
0x1800342fd  lea     r11, [rsp+70h+var_s0]
0x180034302  mov     rbx, [r11+38h]
0x180034306  mov     rsi, [r11+40h]
0x18003430a  mov     rsp, r11
0x18003430d  pop     r15
0x18003430f  pop     r14
0x180034311  pop     r12
0x180034313  pop     rdi
0x180034314  pop     rbp
0x180034315  retn
```
