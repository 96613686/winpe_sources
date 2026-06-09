# CObjectGlobal::GenerateObjects(IWbemServices *,ushort const *,int)

- ea: `0x1400097d0`
- end: `0x140009d6c`
- name: `?GenerateObjects@CObjectGlobal@@QEAAJPEAUIWbemServices@@PEBGH@Z`
- size: `1436`
- prototype: `__int64 __fastcall(CObjectGlobal *__hidden this, struct IWbemServices *, const unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `15`
- tags: `service_task, broker_com_uri`

## callers

- `0x14000ab90`

## callees

- `0x140008fdc`
- `0x14000919c`
- `0x140009294`
- `0x140009638`
- `0x1400097d0`
- `0x140009d74`
- `0x140009de8`
- `0x14000a3d4`
- `0x14000dc3c`
- `0x14000df68`
- `0x14000e04c`
- `0x14000e470`
- `0x14000eca0`
- `0x14000f298`
- `0x140017010`

## import_xrefs

- `msvcrt!_wtol` at `0x140009ac4`
- `msvcrt!_wtol` at `0x140009ac4`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x140009ad0`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x140009b87`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x140009b95`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x140009ba3`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x140009bb1`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x140009c16`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x140009c24`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x140009c32`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x140009c40`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x140009ad0`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x140009b87`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x140009b95`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x140009ba3`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x140009bb1`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x140009c16`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x140009c24`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x140009c32`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x140009c40`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x1400099ff`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x1400099ff`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x140009ccd`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x140009cfd`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x140009ccd`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x140009cfd`

## pseudocode

```c
__int64 __fastcall CObjectGlobal::GenerateObjects(
        CObjectGlobal *this,
        struct IWbemServices *a2,
        const unsigned __int16 *a3,
        int a4)
{
  int v4; // r13d
  CObjectGlobal *v5; // r15
  struct IWbemServices *v6; // rax
  const unsigned __int16 **v7; // rdx
  int PropertyValue; // edi
  unsigned int v9; // r8d
  const unsigned __int16 **v10; // r9
  const unsigned __int16 *v11; // rdx
  CPerformanceObject *v12; // r14
  int Names; // esi
  CObject *v15; // rax
  CObject *v16; // rdi
  unsigned __int16 *v17; // rax
  wchar_t *v18; // rsi
  CObjectGlobal *v19; // rcx
  CObjectGlobal *v20; // rcx
  __int64 *v21; // r14
  __int64 *v22; // rsi
  __int64 *v23; // rdx
  unsigned int v24; // [rsp+20h] [rbp-128h]
  const unsigned __int16 **v25; // [rsp+50h] [rbp-F8h]
  unsigned int v26; // [rsp+58h] [rbp-F0h]
  unsigned int v27; // [rsp+70h] [rbp-D8h] BYREF
  CObject *v28; // [rsp+78h] [rbp-D0h]
  wchar_t *String; // [rsp+80h] [rbp-C8h] BYREF
  int *v30; // [rsp+88h] [rbp-C0h] BYREF
  unsigned int *v31; // [rsp+90h] [rbp-B8h] BYREF
  unsigned int *v32; // [rsp+98h] [rbp-B0h] BYREF
  unsigned int *v33; // [rsp+A0h] [rbp-A8h] BYREF
  unsigned __int16 **v34; // [rsp+A8h] [rbp-A0h] BYREF
  unsigned __int16 **v35; // [rsp+B0h] [rbp-98h] BYREF
  void **v36; // [rsp+B8h] [rbp-90h] BYREF
  CPerformanceObject *v37; // [rsp+C0h] [rbp-88h] BYREF
  void **v38; // [rsp+C8h] [rbp-80h] BYREF
  unsigned __int16 *v39; // [rsp+D0h] [rbp-78h] BYREF
  void **v40; // [rsp+D8h] [rbp-70h] BYREF
  LPCWSTR lpString2; // [rsp+E0h] [rbp-68h] BYREF
  _QWORD v42[2]; // [rsp+E8h] [rbp-60h] BYREF
  int v43; // [rsp+F8h] [rbp-50h]
  __int64 v44; // [rsp+100h] [rbp-48h]
  unsigned int v46; // [rsp+158h] [rbp+10h] BYREF
  int v47; // [rsp+168h] [rbp+20h]

  v47 = a4;
  v4 = a4;
  v5 = this;
  v42[0] = &CPerformanceObjectEnum::`vftable';
  v43 = 0;
  v44 = 0;
  v6 = 0;
  if ( a2 )
    v6 = a2;
  v42[1] = v6;
  PropertyValue = CPerformanceObjectEnum::ExecQuery(
                    (CPerformanceObjectEnum *)v42,
                    (const unsigned __int16 *)a2,
                    a3,
                    a4 != 0 ? 131104 : 32);
  if ( PropertyValue >= 0 )
  {
    while ( !PropertyValue )
    {
      v37 = 0;
      v36 = &__WrapperPtr<CPerformanceObject>::`vftable';
      PropertyValue = CPerformanceObjectEnum::NextObject((CPerformanceObjectEnum *)v42, v7, v9, v10, v24, &v37);
      if ( !PropertyValue )
      {
        if ( v4 )
        {
          v39 = 0;
          v38 = &__WrapperBuffer<unsigned short>::`vftable';
          v12 = v37;
          PropertyValue = CPerformanceObject::GetPropertyValue(v37, v11, &v39);
          if ( PropertyValue < 0 )
          {
            __WrapperBuffer<unsigned short>::~__WrapperBuffer<unsigned short>(&v38);
            __Wrapper<CPerformanceObject>::~__Wrapper<CPerformanceObject>(&v36);
            break;
          }
          v34 = 0;
          v30 = 0;
          v31 = 0;
          v32 = 0;
          v33 = 0;
          v46 = 0;
          v35 = 0;
          v27 = 0;
          Names = CPerformanceObject::GetNames(
                    v12,
                    &v46,
                    &v34,
                    &v30,
                    &v31,
                    &v32,
                    &v33,
                    81,
                    (const unsigned __int16 **)&g_szPropNeed,
                    2u,
                    v25,
                    v26,
                    L"countertype");
          if ( Names < 0
            || (Names = CPerformanceObject::GetNames(v12, &v27, &v35, 0, 0, 0, 0, 84, 0, 0, v25, v26, 0), Names < 0) )
          {
            CWin32DefaultArena::WbemMemFree(v30);
            CWin32DefaultArena::WbemMemFree(v31);
            CWin32DefaultArena::WbemMemFree(v32);
            CWin32DefaultArena::WbemMemFree(v33);
            __Release::ReleaseArrayPtrs((void ***)&v34, &v46);
          }
          else
          {
            v28 = 0;
            try
            {
              v15 = (CObject *)CWin32DefaultArena::WbemMemAlloc(0x60u);
              v16 = v15;
              if ( v15 )
              {
                *(_QWORD *)v15 = &CObject::`vftable';
                *((_QWORD *)v15 + 3) = 0;
                *((_QWORD *)v15 + 2) = &__WrapperARRAY<CLocale *>::`vftable';
                *((_DWORD *)v15 + 8) = 0;
                *((_QWORD *)v15 + 6) = 0;
                *((_QWORD *)v15 + 5) = &__WrapperARRAY<CObjectProperty *>::`vftable';
                *((_DWORD *)v15 + 14) = 0;
                *((_QWORD *)v15 + 9) = 0;
                *((_QWORD *)v15 + 8) = &__WrapperARRAYArrayPtrs<unsigned short *>::`vftable';
                *((_DWORD *)v15 + 20) = 0;
                *((_DWORD *)v15 + 22) = 100;
                v28 = v15;
                v17 = v39;
                v39 = 0;
                *((_QWORD *)v16 + 1) = v17;
                if ( v27 && v35 && *v35 )
                  CObject::SetArrayKeys(v16, v35, v27);
                String = 0;
                CPerformanceObject::GetQualifierValue(v12, L"perfdetail", &String);
                v18 = String;
                if ( String )
                {
                  *((_DWORD *)v16 + 22) = _wtol(String);
                  CWin32DefaultArena::WbemMemFree(v18);
                }
                else
                {
                  *((_DWORD *)v16 + 22) = 0;
                }
                Names = CObject::SetProperties(v16, v12, v34, v30, v31, v32, v33, v46);
                if ( Names < 0 )
                {
                  (**(void (__fastcall ***)(CObject *, __int64))v16)(v16, 1);
                  goto LABEL_24;
                }
              }
              else
              {
                Names = -2147024882;
LABEL_24:
                v28 = 0;
                v16 = 0;
              }
            }
            catch ( ... )
            {
              if ( v28 )
              {
                (**(void (__fastcall ***)(CObject *, __int64))v28)(v28, 1);
                v28 = 0;
              }
              LODWORD(String) = -2147418113;
              v5 = this;
              v4 = v47;
              Names = -2147418113;
              v12 = v37;
              v16 = v28;
            }
            CWin32DefaultArena::WbemMemFree(v30);
            CWin32DefaultArena::WbemMemFree(v31);
            CWin32DefaultArena::WbemMemFree(v32);
            CWin32DefaultArena::WbemMemFree(v33);
            __Release::ReleaseArrayPtrs((void ***)&v34, &v46);
            if ( Names >= 0 )
            {
              Names = CObjectGlobal::AddObject(v5, v16);
              if ( Names < 0 )
              {
                if ( v16 )
                  (**(void (__fastcall ***)(CObject *, __int64))v16)(v16, 1);
              }
              else
              {
                Names = CObjectGlobal::ResolveLocale(v19, v16, v12);
              }
              goto LABEL_32;
            }
          }
          __Release::ReleaseArrayPtrs((void ***)&v35, &v27);
LABEL_32:
          __WrapperBuffer<unsigned short>::~__WrapperBuffer<unsigned short>(&v38);
          PropertyValue = 0;
          if ( Names != 1 )
            PropertyValue = Names;
          goto LABEL_49;
        }
        lpString2 = 0;
        v40 = &__WrapperBuffer<unsigned short>::`vftable';
        PropertyValue = CPerformanceObject::GetPropertyValue(v37, v11, (unsigned __int16 **)&lpString2);
        if ( PropertyValue >= 0 )
        {
          v21 = (__int64 *)*((_QWORD *)v5 + 3);
          v22 = (__int64 *)v21[1];
          while ( !*((_BYTE *)v22 + 25) )
          {
            if ( lstrcmpW((LPCWSTR)v22[4], lpString2) >= 0 )
            {
              v21 = v22;
              v22 = (__int64 *)*v22;
            }
            else
            {
              v22 = (__int64 *)v22[2];
            }
          }
          v23 = (__int64 *)*((_QWORD *)v5 + 3);
          if ( v21 != v23 )
          {
            if ( lstrcmpW(lpString2, (LPCWSTR)v21[4]) >= 0 )
              v23 = v21;
            else
              v23 = (__int64 *)*((_QWORD *)v5 + 3);
          }
          try
          {
            if ( v23 != *((__int64 **)v5 + 3) )
              PropertyValue = CObjectGlobal::ResolveLocale(v20, (struct CObject *)v23[5], v37);
          }
          catch ( ... )
          {
            LODWORD(String) = -2147467259;
            v5 = this;
            v4 = v47;
            PropertyValue = -2147467259;
          }
        }
        __WrapperBuffer<unsigned short>::~__WrapperBuffer<unsigned short>(&v40);
      }
LABEL_49:
      __Wrapper<CPerformanceObject>::~__Wrapper<CPerformanceObject>(&v36);
    }
  }
  CPerformanceObjectEnum::~CPerformanceObjectEnum((CPerformanceObjectEnum *)v42);
  return (unsigned int)PropertyValue;
}

```

## disassembly

```asm
0x1400097d0  mov     r11, rsp
0x1400097d3  mov     [r11+20h], r9d
0x1400097d7  mov     [r11+8], rcx
0x1400097db  push    rbx
0x1400097dc  push    rsi
0x1400097dd  push    rdi
0x1400097de  push    r12
0x1400097e0  push    r13
0x1400097e2  push    r14
0x1400097e4  push    r15
0x1400097e6  sub     rsp, 110h
0x1400097ed  mov     r13d, r9d
0x1400097f0  mov     r15, rcx
0x1400097f3  lea     rax, ??_7CPerformanceObjectEnum@@6B@; const CPerformanceObjectEnum::`vftable'
0x1400097fa  mov     [r11-60h], rax
0x1400097fe  xor     ebx, ebx
0x140009800  mov     [r11-50h], ebx
0x140009804  mov     [r11-48h], rbx
0x140009808  mov     eax, ebx
0x14000980a  test    rdx, rdx
0x14000980d  cmovnz  rax, rdx
0x140009811  mov     [r11-58h], rax
0x140009815  mov     eax, r9d
0x140009818  neg     eax
0x14000981a  sbb     r9d, r9d
0x14000981d  and     r9d, 20000h
0x140009824  add     r9d, 20h ; ' '; int
0x140009828  lea     rcx, [r11-60h]; this
0x14000982c  call    ?ExecQuery@CPerformanceObjectEnum@@QEAAJPEBG0J@Z; CPerformanceObjectEnum::ExecQuery(ushort const *,ushort const *,long)
0x140009831  mov     edi, eax
0x140009833  test    eax, eax
0x140009835  js      loc_1400098D8
0x14000983b  lea     r12, ??_7?$__WrapperBuffer@G@@6B@; const __WrapperBuffer<ushort>::`vftable'
0x140009842  test    edi, edi
0x140009844  jnz     loc_1400098D8
0x14000984a  mov     [rsp+148h+var_88], rbx
0x140009852  lea     rax, ??_7?$__WrapperPtr@VCPerformanceObject@@@@6B@; const __WrapperPtr<CPerformanceObject>::`vftable'
0x140009859  mov     [rsp+148h+var_90], rax
0x140009861  lea     rax, [rsp+148h+var_88]
0x140009869  mov     [rsp+148h+var_120], rax; struct CPerformanceObject **
0x14000986e  lea     rcx, [rsp+148h+var_60]; this
0x140009876  call    ?NextObject@CPerformanceObjectEnum@@QEAAJPEAPEBGK0KPEAPEAVCPerformanceObject@@@Z; CPerformanceObjectEnum::NextObject(ushort const * *,ulong,ushort const * *,ulong,CPerformanceObject * *)
0x14000987b  mov     edi, eax
0x14000987d  test    eax, eax
0x14000987f  jnz     loc_140009D59
0x140009885  test    r13d, r13d
0x140009888  jz      loc_140009C88
0x14000988e  mov     [rsp+148h+var_78], rbx
0x140009896  mov     [rsp+148h+var_80], r12
0x14000989e  mov     r14, [rsp+148h+var_88]
0x1400098a6  lea     r8, [rsp+148h+var_78]; unsigned __int16 **
0x1400098ae  mov     rcx, r14; this
0x1400098b1  call    ?GetPropertyValue@CPerformanceObject@@QEAAJPEBGPEAPEAG@Z; CPerformanceObject::GetPropertyValue(ushort const *,ushort * *)
0x1400098b6  mov     edi, eax
0x1400098b8  test    eax, eax
0x1400098ba  jns     short loc_1400098FA
0x1400098bc  lea     rcx, [rsp+148h+var_80]
0x1400098c4  call    ??1?$__WrapperBuffer@G@@UEAA@XZ; __WrapperBuffer<ushort>::~__WrapperBuffer<ushort>(void)
0x1400098c9  nop
0x1400098ca  lea     rcx, [rsp+148h+var_90]
0x1400098d2  call    ??1?$__Wrapper@VCPerformanceObject@@@@UEAA@XZ; __Wrapper<CPerformanceObject>::~__Wrapper<CPerformanceObject>(void)
0x1400098d7  nop
0x1400098d8  lea     rcx, [rsp+148h+var_60]; this
0x1400098e0  call    ??1CPerformanceObjectEnum@@UEAA@XZ; CPerformanceObjectEnum::~CPerformanceObjectEnum(void)
0x1400098e5  mov     eax, edi
0x1400098e7  add     rsp, 110h
0x1400098ee  pop     r15
0x1400098f0  pop     r14
0x1400098f2  pop     r13
0x1400098f4  pop     r12
0x1400098f6  pop     rdi
0x1400098f7  pop     rsi
0x1400098f8  pop     rbx
0x1400098f9  retn
0x1400098fa  mov     [rsp+148h+var_A0], rbx
0x140009902  mov     [rsp+148h+var_C0], rbx
0x14000990a  mov     [rsp+148h+var_B8], rbx
0x140009912  mov     [rsp+148h+var_B0], rbx
0x14000991a  mov     [rsp+148h+var_A8], rbx
0x140009922  mov     [rsp+148h+arg_8], ebx
0x140009929  mov     [rsp+148h+var_98], rbx
0x140009931  mov     [rsp+148h+var_D8], ebx
0x140009935  lea     rax, aCountertype; "countertype"
0x14000993c  mov     [rsp+148h+var_E8], rax; unsigned __int16 *
0x140009941  mov     [rsp+148h+var_100], 2; unsigned int
0x140009949  lea     rax, ?g_szPropNeed@@3PAPEBGA; ushort const * near * g_szPropNeed
0x140009950  mov     [rsp+148h+var_108], rax; unsigned __int16 **
0x140009955  mov     [rsp+148h+var_110], 51h ; 'Q'; int
0x14000995d  lea     rax, [rsp+148h+var_A8]
0x140009965  mov     [rsp+148h+var_118], rax; unsigned int **
0x14000996a  lea     rax, [rsp+148h+var_B0]
0x140009972  mov     [rsp+148h+var_120], rax; unsigned int **
0x140009977  lea     rax, [rsp+148h+var_B8]
0x14000997f  mov     [rsp+148h+var_128], rax; unsigned int **
0x140009984  lea     r9, [rsp+148h+var_C0]; int **
0x14000998c  lea     r8, [rsp+148h+var_A0]; unsigned __int16 ***
0x140009994  lea     rdx, [rsp+148h+arg_8]; unsigned int *
0x14000999c  mov     rcx, r14; this
0x14000999f  call    ?GetNames@CPerformanceObject@@QEAAJPEAKPEAPEAPEAGPEAPEAJPEAPEAK33JPEAPEBGK4KPEBG@Z; CPerformanceObject::GetNames(ulong *,ushort * * *,long * *,ulong * *,ulong * *,ulong * *,long,ushort const * *,ulong,ushort const * *,ulong,ushort const *)
0x1400099a4  mov     esi, eax
0x1400099a6  test    eax, eax
0x1400099a8  js      loc_140009C0E
0x1400099ae  mov     [rsp+148h+var_E8], rbx; unsigned __int16 *
0x1400099b3  mov     [rsp+148h+var_100], ebx; unsigned int
0x1400099b7  mov     [rsp+148h+var_108], rbx; unsigned __int16 **
0x1400099bc  mov     [rsp+148h+var_110], 54h ; 'T'; int
0x1400099c4  mov     [rsp+148h+var_118], rbx; unsigned int **
0x1400099c9  mov     [rsp+148h+var_120], rbx; unsigned int **
0x1400099ce  mov     [rsp+148h+var_128], rbx; unsigned int **
0x1400099d3  xor     r9d, r9d; int **
0x1400099d6  lea     r8, [rsp+148h+var_98]; unsigned __int16 ***
0x1400099de  lea     rdx, [rsp+148h+var_D8]; unsigned int *
0x1400099e3  mov     rcx, r14; this
0x1400099e6  call    ?GetNames@CPerformanceObject@@QEAAJPEAKPEAPEAPEAGPEAPEAJPEAPEAK33JPEAPEBGK4KPEBG@Z; CPerformanceObject::GetNames(ulong *,ushort * * *,long * *,ulong * *,ulong * *,ulong * *,long,ushort const * *,ulong,ushort const * *,ulong,ushort const *)
0x1400099eb  mov     esi, eax
0x1400099ed  test    eax, eax
0x1400099ef  js      loc_140009C0E
0x1400099f5  mov     [rsp+148h+var_D0], rbx
0x1400099fa  mov     ecx, 60h ; '`'
0x1400099ff  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x140009a05  mov     rdi, rax
0x140009a08  test    rax, rax
0x140009a0b  jz      loc_140009B43
0x140009a11  lea     rax, ??_7CObject@@6B@; const CObject::`vftable'
0x140009a18  mov     [rdi], rax
0x140009a1b  mov     [rdi+18h], rbx
0x140009a1f  lea     rax, ??_7?$__WrapperARRAY@PEAVCLocale@@@@6B@; const __WrapperARRAY<CLocale *>::`vftable'
0x140009a26  mov     [rdi+10h], rax
0x140009a2a  mov     [rdi+20h], ebx
0x140009a2d  mov     [rdi+30h], rbx
0x140009a31  lea     rax, ??_7?$__WrapperARRAY@PEAVCObjectProperty@@@@6B@; const __WrapperARRAY<CObjectProperty *>::`vftable'
0x140009a38  mov     [rdi+28h], rax
0x140009a3c  mov     [rdi+38h], ebx
0x140009a3f  mov     [rdi+48h], rbx
0x140009a43  lea     rax, ??_7?$__WrapperARRAYArrayPtrs@PEAG@@6B@; const __WrapperARRAYArrayPtrs<ushort *>::`vftable'
0x140009a4a  mov     [rdi+40h], rax
0x140009a4e  mov     [rdi+50h], ebx
0x140009a51  mov     dword ptr [rdi+58h], 64h ; 'd'
0x140009a58  mov     [rsp+148h+var_D0], rdi
0x140009a5d  mov     rax, [rsp+148h+var_78]
0x140009a65  mov     [rsp+148h+var_78], rbx
0x140009a6d  mov     [rdi+8], rax
0x140009a71  mov     r8d, [rsp+148h+var_D8]; unsigned int
0x140009a76  test    r8d, r8d
0x140009a79  jz      short loc_140009A95
0x140009a7b  mov     rdx, [rsp+148h+var_98]; unsigned __int16 **
0x140009a83  test    rdx, rdx
0x140009a86  jz      short loc_140009A95
0x140009a88  cmp     [rdx], rbx
0x140009a8b  jz      short loc_140009A95
0x140009a8d  mov     rcx, rdi; this
0x140009a90  call    ?SetArrayKeys@CObject@@QEAAXPEAPEAGK@Z; CObject::SetArrayKeys(ushort * *,ulong)
0x140009a95  mov     [rsp+148h+String], rbx
0x140009a9d  lea     r8, [rsp+148h+String]; unsigned __int16 **
0x140009aa5  lea     rdx, aPerfdetail; "perfdetail"
0x140009aac  mov     rcx, r14; this
0x140009aaf  call    ?GetQualifierValue@CPerformanceObject@@QEAAJPEBGPEAPEAG@Z; CPerformanceObject::GetQualifierValue(ushort const *,ushort * *)
0x140009ab4  mov     rsi, [rsp+148h+String]
0x140009abc  test    rsi, rsi
0x140009abf  jz      short loc_140009AD8
0x140009ac1  mov     rcx, rsi; String
0x140009ac4  call    cs:__imp__wtol
0x140009aca  mov     [rdi+58h], eax
0x140009acd  mov     rcx, rsi
0x140009ad0  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x140009ad6  jmp     short loc_140009ADB
0x140009ad8  mov     [rdi+58h], ebx
0x140009adb  mov     eax, [rsp+148h+arg_8]
0x140009ae2  mov     [rsp+148h+var_110], eax; unsigned int
0x140009ae6  mov     rax, [rsp+148h+var_A8]
0x140009aee  mov     [rsp+148h+var_118], rax; unsigned int *
0x140009af3  mov     rax, [rsp+148h+var_B0]
0x140009afb  mov     [rsp+148h+var_120], rax; unsigned int *
0x140009b00  mov     rax, [rsp+148h+var_B8]
0x140009b08  mov     [rsp+148h+var_128], rax; unsigned int *
0x140009b0d  mov     r9, [rsp+148h+var_C0]; int *
0x140009b15  mov     r8, [rsp+148h+var_A0]; unsigned __int16 **
0x140009b1d  mov     rdx, r14; struct CPerformanceObject *
0x140009b20  mov     rcx, rdi; this
0x140009b23  call    ?SetProperties@CObject@@QEAAJPEAVCPerformanceObject@@PEAPEAGPEAJPEAK33K@Z; CObject::SetProperties(CPerformanceObject *,ushort * *,long *,ulong *,ulong *,ulong *,ulong)
0x140009b28  mov     esi, eax
0x140009b2a  test    eax, eax
0x140009b2c  jns     short loc_140009B50
0x140009b2e  mov     rax, [rdi]
0x140009b31  mov     edx, 1
0x140009b36  mov     rcx, rdi
0x140009b39  mov     rax, [rax]
0x140009b3c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140009b41  jmp     short loc_140009B48
0x140009b43  mov     esi, 8007000Eh
0x140009b48  mov     [rsp+148h+var_D0], rbx
0x140009b4d  mov     rdi, rbx
0x140009b50  jmp     short loc_140009B7F
0x140009b52  xor     ebx, ebx
0x140009b54  lea     r12, ??_7?$__WrapperBuffer@G@@6B@; const __WrapperBuffer<ushort>::`vftable'
0x140009b5b  mov     r15, [rsp+148h+arg_0]
0x140009b63  mov     r13d, [rsp+148h+arg_18]
0x140009b6b  mov     esi, dword ptr [rsp+148h+String]
0x140009b72  mov     r14, [rsp+148h+var_88]
0x140009b7a  mov     rdi, [rsp+148h+var_D0]
0x140009b7f  mov     rcx, [rsp+148h+var_C0]
0x140009b87  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x140009b8d  mov     rcx, [rsp+148h+var_B8]
0x140009b95  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x140009b9b  mov     rcx, [rsp+148h+var_B0]
0x140009ba3  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x140009ba9  mov     rcx, [rsp+148h+var_A8]
0x140009bb1  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x140009bb7  lea     rdx, [rsp+148h+arg_8]; unsigned int *
0x140009bbf  lea     rcx, [rsp+148h+var_A0]; void ***
0x140009bc7  call    ?ReleaseArrayPtrs@__Release@@SAJPEAPEAPEAXPEAK@Z; __Release::ReleaseArrayPtrs(void * * *,ulong *)
0x140009bcc  test    esi, esi
0x140009bce  js      loc_140009C5B
0x140009bd4  mov     rdx, rdi; struct CObject *
0x140009bd7  mov     rcx, r15; this
0x140009bda  call    ?AddObject@CObjectGlobal@@AEAAJPEAVCObject@@@Z; CObjectGlobal::AddObject(CObject *)
0x140009bdf  mov     esi, eax
0x140009be1  test    eax, eax
0x140009be3  js      short loc_140009BF4
0x140009be5  mov     r8, r14; struct CPerformanceObject *
0x140009be8  mov     rdx, rdi; struct CObject *
0x140009beb  call    ?ResolveLocale@CObjectGlobal@@AEAAJPEAVCObject@@PEAVCPerformanceObject@@@Z; CObjectGlobal::ResolveLocale(CObject *,CPerformanceObject *)
0x140009bf0  mov     esi, eax
0x140009bf2  jmp     short loc_140009C6E
0x140009bf4  test    rdi, rdi
0x140009bf7  jz      short loc_140009C6E
0x140009bf9  mov     rax, [rdi]
0x140009bfc  mov     edx, 1
0x140009c01  mov     rcx, rdi
0x140009c04  mov     rax, [rax]
0x140009c07  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140009c0c  jmp     short loc_140009C6E
0x140009c0e  mov     rcx, [rsp+148h+var_C0]
0x140009c16  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x140009c1c  mov     rcx, [rsp+148h+var_B8]
0x140009c24  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x140009c2a  mov     rcx, [rsp+148h+var_B0]
0x140009c32  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x140009c38  mov     rcx, [rsp+148h+var_A8]
0x140009c40  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x140009c46  lea     rdx, [rsp+148h+arg_8]; unsigned int *
0x140009c4e  lea     rcx, [rsp+148h+var_A0]; void ***
0x140009c56  call    ?ReleaseArrayPtrs@__Release@@SAJPEAPEAPEAXPEAK@Z; __Release::ReleaseArrayPtrs(void * * *,ulong *)
0x140009c5b  lea     rdx, [rsp+148h+var_D8]; unsigned int *
0x140009c60  lea     rcx, [rsp+148h+var_98]; void ***
0x140009c68  call    ?ReleaseArrayPtrs@__Release@@SAJPEAPEAPEAXPEAK@Z; __Release::ReleaseArrayPtrs(void * * *,ulong *)
0x140009c6d  nop
0x140009c6e  lea     rcx, [rsp+148h+var_80]
0x140009c76  call    ??1?$__WrapperBuffer@G@@UEAA@XZ; __WrapperBuffer<ushort>::~__WrapperBuffer<ushort>(void)
0x140009c7b  mov     edi, ebx
0x140009c7d  cmp     esi, 1
0x140009c80  cmovnz  edi, esi
0x140009c83  jmp     loc_140009D59
0x140009c88  mov     [rsp+148h+lpString2], rbx
0x140009c90  mov     [rsp+148h+var_70], r12
0x140009c98  lea     r8, [rsp+148h+lpString2]; unsigned __int16 **
0x140009ca0  mov     rcx, [rsp+148h+var_88]; this
0x140009ca8  call    ?GetPropertyValue@CPerformanceObject@@QEAAJPEBGPEAPEAG@Z; CPerformanceObject::GetPropertyValue(ushort const *,ushort * *)
0x140009cad  mov     edi, eax
0x140009caf  test    eax, eax
0x140009cb1  js      loc_140009D4B
0x140009cb7  mov     r14, [r15+18h]
0x140009cbb  mov     rsi, [r14+8]
0x140009cbf  jmp     short loc_140009CE3
0x140009cc1  mov     rdx, [rsp+148h+lpString2]; lpString2
0x140009cc9  mov     rcx, [rsi+20h]; lpString1
0x140009ccd  call    cs:__imp_lstrcmpW
0x140009cd3  test    eax, eax
0x140009cd5  jns     short loc_140009CDD
0x140009cd7  mov     rsi, [rsi+10h]
0x140009cdb  jmp     short loc_140009CE3
0x140009cdd  mov     r14, rsi
0x140009ce0  mov     rsi, [rsi]
0x140009ce3  cmp     [rsi+19h], bl
0x140009ce6  jz      short loc_140009CC1
0x140009ce8  mov     rdx, [r15+18h]
0x140009cec  cmp     r14, rdx
0x140009cef  jz      short loc_140009D10
0x140009cf1  mov     rdx, [r14+20h]; lpString2
0x140009cf5  mov     rcx, [rsp+148h+lpString2]; lpString1
0x140009cfd  call    cs:__imp_lstrcmpW
0x140009d03  test    eax, eax
0x140009d05  jns     short loc_140009D0D
0x140009d07  mov     rdx, [r15+18h]
0x140009d0b  jmp     short loc_140009D10
0x140009d0d  mov     rdx, r14
0x140009d10  cmp     rdx, [r15+18h]
0x140009d14  jz      short loc_140009D29
0x140009d16  mov     r8, [rsp+148h+var_88]; struct CPerformanceObject *
0x140009d1e  mov     rdx, [rdx+28h]; struct CObject *
0x140009d22  call    ?ResolveLocale@CObjectGlobal@@AEAAJPEAVCObject@@PEAVCPerformanceObject@@@Z; CObjectGlobal::ResolveLocale(CObject *,CPerformanceObject *)
0x140009d27  mov     edi, eax
0x140009d29  jmp     short loc_140009D4B
0x140009d2b  xor     ebx, ebx
0x140009d2d  lea     r12, ??_7?$__WrapperBuffer@G@@6B@; const __WrapperBuffer<ushort>::`vftable'
0x140009d34  mov     r15, [rsp+148h+arg_0]
0x140009d3c  mov     r13d, [rsp+148h+arg_18]
0x140009d44  mov     edi, dword ptr [rsp+148h+String]
0x140009d4b  lea     rcx, [rsp+148h+var_70]
0x140009d53  call    ??1?$__WrapperBuffer@G@@UEAA@XZ; __WrapperBuffer<ushort>::~__WrapperBuffer<ushort>(void)
  ... truncated ...
```
