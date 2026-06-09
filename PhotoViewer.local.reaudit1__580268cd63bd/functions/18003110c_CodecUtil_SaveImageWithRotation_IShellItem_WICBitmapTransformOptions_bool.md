# CodecUtil::SaveImageWithRotation(IShellItem *,WICBitmapTransformOptions,bool *)

- ea: `0x18003110c`
- end: `0x1800313b0`
- name: `?SaveImageWithRotation@CodecUtil@@YAJPEAUIShellItem@@W4WICBitmapTransformOptions@@PEA_N@Z`
- size: `676`
- prototype: `__int64 __fastcall(CodecUtil *__hidden this, struct IShellItem *, enum WICBitmapTransformOptions, bool *)`
- caller_count: `1`
- callee_count: `9`
- tags: `service_task`

## callers

- `0x1800496ec`

## callees

- `0x180004908`
- `0x18002e5a8`
- `0x18003110c`
- `0x1800313b8`
- `0x180031480`
- `0x18007847c`
- `0x180078950`
- `0x180078e60`
- `0x180080010`

## import_xrefs

- `KERNEL32!GetSystemTimeAsFileTime` at `0x180031280`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x180031280`
- `KERNEL32!FileTimeToDosDateTime` at `0x18003129c`
- `KERNEL32!FileTimeToDosDateTime` at `0x1800312c3`
- `KERNEL32!FileTimeToDosDateTime` at `0x18003129c`
- `KERNEL32!FileTimeToDosDateTime` at `0x1800312c3`
- `ole32!CoTaskMemFree` at `0x180031393`
- `ole32!CoTaskMemFree` at `0x180031393`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CodecUtil::SaveImageWithRotation(
        CodecUtil *this,
        struct IShellItem *a2,
        const unsigned __int16 *a3,
        bool *a4)
{
  unsigned int v4; // r14d
  int v6; // esi
  int AsUInt32With; // ebx
  __int64 v8; // r8
  unsigned int v9; // edx
  BOOL v10; // eax
  BOOL v11; // eax
  struct _FILETIME *v12; // r8
  __int64 v13; // rax
  int v14; // ecx
  CodecUtilPrivate *v15; // r9
  WORD v17[2]; // [rsp+30h] [rbp-40h] BYREF
  WORD FatTime; // [rsp+34h] [rbp-3Ch] BYREF
  FILETIME FileTime; // [rsp+38h] [rbp-38h] BYREF
  __int64 v20; // [rsp+40h] [rbp-30h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+48h] [rbp-28h] BYREF
  PROPERTYKEY v22; // [rsp+50h] [rbp-20h] BYREF
  unsigned __int16 *v23; // [rsp+A0h] [rbp+30h] BYREF
  struct IWICImagingFactory FatDate; // [rsp+A8h] [rbp+38h] BYREF

  v23 = (unsigned __int16 *)a3;
  v4 = (unsigned int)a2;
  if ( !CodecUtil::IsOrientationSupported(this, a2) )
    goto LABEL_21;
  FileTime = 0;
  v6 = CodecUtil::GetSetLastWriteTime(this, &FileTime, 0);
  v20 = 0;
  v23 = 0;
  AsUInt32With = (**(__int64 (__fastcall ***)(CodecUtil *, GUID *, unsigned __int16 **))this)(
                   this,
                   &GUID_7e9fb0d3_919f_4307_ab2e_9b1860310c93,
                   &v23);
  if ( AsUInt32With >= 0 )
  {
    AsUInt32With = (*(__int64 (__fastcall **)(unsigned __int16 *, __int64, GUID *, __int64 *))(*(_QWORD *)v23 + 64LL))(
                     v23,
                     2,
                     &GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99,
                     &v20);
    (*(void (__fastcall **)(unsigned __int16 *))(*(_QWORD *)v23 + 16LL))(v23);
    if ( AsUInt32With >= 0 )
    {
      LODWORD(v23) = 0;
      v22 = PKEY_Photo_Orientation;
      AsUInt32With = CPropertyStoreHelperBase<IPropertyStore>::GetAsUInt32WithDefault<_tagpropertykey>(
                       &v20,
                       &v22,
                       v8,
                       &v23);
      if ( AsUInt32With >= 0 )
      {
        v9 = (unsigned int)v23;
        if ( (unsigned int)v23 > 8 )
        {
          v9 = 1;
          LODWORD(v23) = 1;
        }
        LOWORD(v22.fmtid.Data1) = 19;
        *(_DWORD *)v22.fmtid.Data4 = *((unsigned __int16 *)qword_18008DB58 + v9 + (unsigned __int64)(v4 != 1 ? 9 : 0));
        AsUInt32With = (*(__int64 (__fastcall **)(__int64, const PROPERTYKEY *, PROPERTYKEY *))(*(_QWORD *)v20 + 48LL))(
                         v20,
                         &PKEY_Photo_Orientation,
                         &v22);
        if ( AsUInt32With >= 0 )
        {
          AsUInt32With = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v20 + 56LL))(v20);
          if ( AsUInt32With >= 0 && v6 >= 0 )
          {
            SystemTimeAsFileTime = 0;
            GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
            LOWORD(FatDate.lpVtbl) = 0;
            FatTime = 0;
            v10 = FileTimeToDosDateTime(&SystemTimeAsFileTime, (LPWORD)&FatDate, &FatTime);
            if ( (int)ResultFromWin32Bool(v10) >= 0 )
            {
              LOWORD(v23) = 0;
              v17[0] = 0;
              v11 = FileTimeToDosDateTime(&FileTime, (LPWORD)&v23, v17);
              if ( (int)ResultFromWin32Bool(v11) >= 0
                && (LOWORD(FatDate.lpVtbl) == (_WORD)v23 && FatTime == v17[0]
                 || *(_QWORD *)&SystemTimeAsFileTime < *(unsigned __int64 *)&FileTime) )
              {
                v13 = *(_QWORD *)&FileTime + 20000001LL;
                FileTime.dwLowDateTime += 20000001;
                FileTime.dwHighDateTime = HIDWORD(v13);
                LOBYTE(v12) = 1;
                CodecUtil::GetSetLastWriteTime(this, &FileTime, v12);
              }
            }
          }
        }
      }
    }
  }
  if ( v20 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
  if ( AsUInt32With < 0 )
  {
    if ( (unsigned int)(AsUInt32With + 2147287038) > 0x1F
      || (v14 = -1073610743, !_bittest(&v14, AsUInt32With + 2147287038)) )
    {
LABEL_21:
      v23 = 0;
      AsUInt32With = (*(__int64 (__fastcall **)(CodecUtil *, __int64, unsigned __int16 **))(*(_QWORD *)this + 40LL))(
                       this,
                       2147844096LL,
                       &v23);
      if ( AsUInt32With >= 0 )
      {
        Base::Path::Path((Base::Path *)&FatDate, v23);
        AsUInt32With = CodecUtil::CopyImageWithRotation(&FatDate, (LPCWSTR *)&FatDate, (const struct Path *)v4, v15);
        Base::String::~String((Base::String *)&FatDate);
      }
      CoTaskMemFree(v23);
    }
  }
  return (unsigned int)AsUInt32With;
}

```

## disassembly

```asm
0x18003110c  mov     [rsp-18h+arg_0], rbx
0x180031111  mov     [rsp-18h+arg_8], rsi
0x180031116  mov     [rsp-18h+arg_10], r8
0x18003111b  push    rbp
0x18003111c  push    rdi
0x18003111d  push    r14
0x18003111f  mov     rbp, rsp
0x180031122  sub     rsp, 70h
0x180031126  mov     r14d, edx
0x180031129  mov     rdi, rcx
0x18003112c  call    ?IsOrientationSupported@CodecUtil@@YA_NPEAUIShellItem@@@Z; CodecUtil::IsOrientationSupported(IShellItem *)
0x180031131  test    al, al
0x180031133  jz      loc_180031341
0x180031139  mov     qword ptr [rbp+FileTime.dwLowDateTime], 0
0x180031141  xor     r8d, r8d; struct _FILETIME *
0x180031144  lea     rdx, [rbp+FileTime]; struct IShellItem *
0x180031148  mov     rcx, rdi; this
0x18003114b  call    ?GetSetLastWriteTime@CodecUtil@@YAJPEAUIShellItem@@PEAU_FILETIME@@_N@Z; CodecUtil::GetSetLastWriteTime(IShellItem *,_FILETIME *,bool)
0x180031150  mov     esi, eax
0x180031152  mov     [rbp+var_30], 0
0x18003115a  mov     [rbp+arg_10], 0
0x180031162  mov     rcx, [rdi]
0x180031165  mov     rax, [rcx]
0x180031168  lea     r8, [rbp+arg_10]
0x18003116c  lea     rdx, _GUID_7e9fb0d3_919f_4307_ab2e_9b1860310c93
0x180031173  mov     rcx, rdi
0x180031176  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003117b  mov     ebx, eax
0x18003117d  test    eax, eax
0x18003117f  js      loc_180031312
0x180031185  mov     rcx, [rbp+arg_10]
0x180031189  mov     rax, [rcx]
0x18003118c  lea     r9, [rbp+var_30]
0x180031190  lea     r8, _GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99
0x180031197  mov     edx, 2
0x18003119c  mov     rax, [rax+40h]
0x1800311a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800311a5  mov     ebx, eax
0x1800311a7  mov     rcx, [rbp+arg_10]
0x1800311ab  mov     rax, [rcx]
0x1800311ae  mov     rax, [rax+10h]
0x1800311b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800311b7  test    ebx, ebx
0x1800311b9  js      loc_180031312
0x1800311bf  mov     dword ptr [rbp+arg_10], 0
0x1800311c6  movups  xmm0, xmmword ptr cs:PKEY_Photo_Orientation.fmtid.Data1
0x1800311cd  movaps  [rbp+var_20], xmm0
0x1800311d1  mov     eax, cs:PKEY_Photo_Orientation.pid
0x1800311d7  mov     [rbp+var_10], eax
0x1800311da  lea     r9, [rbp+arg_10]
0x1800311de  lea     rdx, [rbp+var_20]
0x1800311e2  lea     rcx, [rbp+var_30]
0x1800311e6  call    ??$GetAsUInt32WithDefault@U_tagpropertykey@@@?$CPropertyStoreHelperBase@UIPropertyStore@@@@QEBAJU_tagpropertykey@@KPEAK@Z; CPropertyStoreHelperBase<IPropertyStore>::GetAsUInt32WithDefault<_tagpropertykey>(_tagpropertykey,ulong,ulong *)
0x1800311eb  mov     ebx, eax
0x1800311ed  test    eax, eax
0x1800311ef  js      loc_180031312
0x1800311f5  mov     edx, dword ptr [rbp+arg_10]
0x1800311f8  cmp     edx, 8
0x1800311fb  jbe     short loc_180031205
0x1800311fd  mov     edx, 1
0x180031202  mov     dword ptr [rbp+arg_10], edx
0x180031205  mov     eax, 13h
0x18003120a  mov     word ptr [rbp+var_20], ax
0x18003120e  lea     eax, [r14-1]
0x180031212  neg     eax
0x180031214  sbb     rcx, rcx
0x180031217  and     ecx, 9
0x18003121a  mov     eax, edx
0x18003121c  add     rcx, rax
0x18003121f  lea     rax, qword_18008DB58
0x180031226  movzx   eax, word ptr [rax+rcx*2]
0x18003122a  mov     dword ptr [rbp+var_20+8], eax
0x18003122d  mov     rcx, [rbp+var_30]
0x180031231  mov     rax, [rcx]
0x180031234  lea     r8, [rbp+var_20]
0x180031238  lea     rdx, PKEY_Photo_Orientation
0x18003123f  mov     rax, [rax+30h]
0x180031243  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031248  mov     ebx, eax
0x18003124a  test    eax, eax
0x18003124c  js      loc_180031312
0x180031252  mov     rcx, [rbp+var_30]
0x180031256  mov     rax, [rcx]
0x180031259  mov     rax, [rax+38h]
0x18003125d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031262  mov     ebx, eax
0x180031264  test    eax, eax
0x180031266  js      loc_180031312
0x18003126c  test    esi, esi
0x18003126e  js      loc_180031312
0x180031274  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], 0
0x18003127c  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180031280  call    cs:__imp_GetSystemTimeAsFileTime
0x180031286  xor     eax, eax
0x180031288  mov     word ptr [rbp+FatDate], ax
0x18003128c  mov     [rbp+FatTime], ax
0x180031290  lea     r8, [rbp+FatTime]; lpFatTime
0x180031294  lea     rdx, [rbp+FatDate]; lpFatDate
0x180031298  lea     rcx, [rbp+SystemTimeAsFileTime]; lpFileTime
0x18003129c  call    cs:__imp_FileTimeToDosDateTime
0x1800312a2  mov     ecx, eax; int
0x1800312a4  call    ?ResultFromWin32Bool@@YAJH@Z; ResultFromWin32Bool(int)
0x1800312a9  test    eax, eax
0x1800312ab  js      short loc_180031312
0x1800312ad  xor     eax, eax
0x1800312af  mov     word ptr [rbp+arg_10], ax
0x1800312b3  mov     [rbp+var_40], ax
0x1800312b7  lea     r8, [rbp+var_40]; lpFatTime
0x1800312bb  lea     rdx, [rbp+arg_10]; lpFatDate
0x1800312bf  lea     rcx, [rbp+FileTime]; lpFileTime
0x1800312c3  call    cs:__imp_FileTimeToDosDateTime
0x1800312c9  mov     ecx, eax; int
0x1800312cb  call    ?ResultFromWin32Bool@@YAJH@Z; ResultFromWin32Bool(int)
0x1800312d0  test    eax, eax
0x1800312d2  js      short loc_180031312
0x1800312d4  mov     rax, qword ptr [rbp+FileTime.dwLowDateTime]
0x1800312d8  movzx   ecx, word ptr [rbp+arg_10]
0x1800312dc  cmp     word ptr [rbp+FatDate], cx
0x1800312e0  jnz     short loc_1800312EC
0x1800312e2  movzx   ecx, [rbp+var_40]
0x1800312e6  cmp     [rbp+FatTime], cx
0x1800312ea  jz      short loc_1800312F2
0x1800312ec  cmp     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x1800312f0  jnb     short loc_180031312
0x1800312f2  add     rax, 1312D01h
0x1800312f8  mov     [rbp+FileTime.dwLowDateTime], eax
0x1800312fb  shr     rax, 20h
0x1800312ff  mov     [rbp+FileTime.dwHighDateTime], eax
0x180031302  mov     r8b, 1; struct _FILETIME *
0x180031305  lea     rdx, [rbp+FileTime]; struct IShellItem *
0x180031309  mov     rcx, rdi; this
0x18003130c  call    ?GetSetLastWriteTime@CodecUtil@@YAJPEAUIShellItem@@PEAU_FILETIME@@_N@Z; CodecUtil::GetSetLastWriteTime(IShellItem *,_FILETIME *,bool)
0x180031311  nop
0x180031312  mov     rcx, [rbp+var_30]
0x180031316  test    rcx, rcx
0x180031319  jz      short loc_180031328
0x18003131b  mov     rax, [rcx]
0x18003131e  mov     rax, [rax+10h]
0x180031322  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031327  nop
0x180031328  test    ebx, ebx
0x18003132a  jns     short loc_180031399
0x18003132c  lea     eax, [rbx+7FFCFFFEh]
0x180031332  cmp     eax, 1Fh
0x180031335  ja      short loc_180031341
0x180031337  mov     ecx, 0C0020009h
0x18003133c  bt      ecx, eax
0x18003133f  jb      short loc_180031399
0x180031341  mov     [rbp+arg_10], 0
0x180031349  mov     rax, [rdi]
0x18003134c  lea     r8, [rbp+arg_10]
0x180031350  mov     edx, 80058000h
0x180031355  mov     rcx, rdi
0x180031358  mov     rax, [rax+28h]
0x18003135c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031361  mov     ebx, eax
0x180031363  test    eax, eax
0x180031365  js      short loc_18003138F
0x180031367  mov     rdx, [rbp+arg_10]; unsigned __int16 *
0x18003136b  lea     rcx, [rbp+FatDate]; this
0x18003136f  call    ??0Path@Base@@QEAA@PEBG@Z; Base::Path::Path(ushort const *)
0x180031374  mov     r8d, r14d; struct Path *
0x180031377  lea     rdx, [rbp+FatDate]; struct Path *
0x18003137b  lea     rcx, [rbp+FatDate]; this
0x18003137f  call    ?CopyImageWithRotation@CodecUtil@@YAJAEBVPath@Base@@0W4WICBitmapTransformOptions@@PEA_N@Z; CodecUtil::CopyImageWithRotation(Base::Path const &,Base::Path const &,WICBitmapTransformOptions,bool *)
0x180031384  mov     ebx, eax
0x180031386  lea     rcx, [rbp+FatDate]; this
0x18003138a  call    ??1String@Base@@QEAA@XZ; Base::String::~String(void)
0x18003138f  mov     rcx, [rbp+arg_10]; pv
0x180031393  call    cs:__imp_CoTaskMemFree
0x180031399  mov     eax, ebx
0x18003139b  lea     r11, [rsp+70h+var_s0]
0x1800313a0  mov     rbx, [r11+20h]
0x1800313a4  mov     rsi, [r11+28h]
0x1800313a8  mov     rsp, r11
0x1800313ab  pop     r14
0x1800313ad  pop     rdi
0x1800313ae  pop     rbp
0x1800313af  retn
```
