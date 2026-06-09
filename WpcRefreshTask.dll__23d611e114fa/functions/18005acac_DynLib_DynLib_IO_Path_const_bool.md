# DynLib::DynLib(IO::Path const &,bool)

- ea: `0x18005acac`
- end: `0x18005ae25`
- name: `??0DynLib@@QEAA@AEBVPath@IO@@_N@Z`
- size: `377`
- prototype: `DynLib *(DynLib *__hidden this, const struct Path *, bool)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting`

## callers

- `0x180009ed0`

## callees

- `0x180006108`
- `0x180006ee0`
- `0x18000e93c`
- `0x180035e0c`
- `0x180059820`
- `0x18005acac`
- `0x18005afc8`
- `0x1800ae010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18005acf9`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18005acf9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005adb8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005adb8`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
DynLib *__fastcall DynLib::DynLib(DynLib *this, const WCHAR *a2, char a3)
{
  const WCHAR *v5; // rcx
  HMODULE Library; // rax
  HMODULE v7; // rbx
  volatile signed __int32 *v8; // rbx
  signed int LastError; // eax
  unsigned int v11; // ebx
  __int64 v12; // rax
  int v13; // eax
  __int64 v14; // rdx
  int v15; // r8d
  _QWORD pExceptionObject[2]; // [rsp+30h] [rbp-38h] BYREF
  char v17; // [rsp+40h] [rbp-28h]
  _DWORD *v18; // [rsp+70h] [rbp+8h]
  char v19; // [rsp+80h] [rbp+18h] BYREF

  v19 = a3;
  *(_QWORD *)this = &DynLib::`vftable';
  *((_QWORD *)this + 1) = 0;
  *((_QWORD *)this + 2) = 0;
  if ( *((_QWORD *)a2 + 3) <= 7u )
    v5 = a2;
  else
    v5 = *(const WCHAR **)a2;
  Library = LoadLibraryExW(v5, 0, 2u);
  v7 = Library;
  if ( !Library )
  {
    LastError = GetLastError();
    v11 = LastError;
    if ( LastError > 0 )
      v11 = (unsigned __int16)LastError | 0x80070000;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v12 = std::array<unsigned short,16>::data(a2);
      v13 = std::wstring::c_str(v12);
      WPP_SF_Sld(*(_QWORD *)(v14 + 16), v14, v15, v13);
    }
    ErrorCodeException::ErrorCodeException((ErrorCodeException *)pExceptionObject, v11);
    throw (ErrorCodeException *)pExceptionObject;
  }
  v19 = 0;
  pExceptionObject[0] = Library;
  pExceptionObject[1] = &v19;
  v17 = 1;
  v18 = operator new(0x18u);
  *(_OWORD *)v18 = 0;
  v18[2] = 1;
  v18[3] = 1;
  *(_QWORD *)v18 = &std::_Ref_count_resource<HINSTANCE__ *,_lambda_6bfbb92090c379a9aabfb7129ba6d39d_>::`vftable';
  *((_QWORD *)v18 + 2) = v7;
  *((_QWORD *)this + 1) = v7;
  v8 = (volatile signed __int32 *)*((_QWORD *)this + 2);
  *((_QWORD *)this + 2) = v18;
  if ( v8 )
  {
    if ( _InterlockedExchangeAdd(v8 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v8)(v8);
      if ( _InterlockedExchangeAdd(v8 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v8 + 8LL))(v8);
    }
  }
  return this;
}

```

## disassembly

```asm
0x18005acac  mov     rax, rsp
0x18005acaf  mov     [rax+10h], rbx
0x18005acb3  mov     [rax+20h], rsi
0x18005acb7  mov     [rax+18h], r8b
0x18005acbb  mov     [rax+8], rcx
0x18005acbf  push    rdi
0x18005acc0  sub     rsp, 60h
0x18005acc4  mov     rsi, rdx
0x18005acc7  mov     rdi, rcx
0x18005acca  lea     rax, ??_7DynLib@@6B@; const DynLib::`vftable'
0x18005acd1  mov     [rcx], rax
0x18005acd4  mov     qword ptr [rcx+8], 0
0x18005acdc  mov     qword ptr [rcx+10h], 0
0x18005ace4  cmp     qword ptr [rdx+18h], 7
0x18005ace9  jbe     short loc_18005ACF0
0x18005aceb  mov     rcx, [rdx]
0x18005acee  jmp     short loc_18005ACF3
0x18005acf0  mov     rcx, rsi; lpLibFileName
0x18005acf3  xor     edx, edx; hFile
0x18005acf5  lea     r8d, [rdx+2]; dwFlags
0x18005acf9  call    cs:__imp_LoadLibraryExW
0x18005acff  mov     rbx, rax
0x18005ad02  test    rax, rax
0x18005ad05  jz      loc_18005ADB8
0x18005ad0b  mov     [rsp+68h+arg_10], 0
0x18005ad13  mov     [rsp+68h+pExceptionObject], rax
0x18005ad18  lea     rax, [rsp+68h+arg_10]
0x18005ad20  mov     [rsp+68h+var_30], rax
0x18005ad25  mov     [rsp+68h+var_28], 1
0x18005ad2a  mov     ecx, 18h; Size
0x18005ad2f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18005ad34  mov     [rsp+68h+arg_0], rax
0x18005ad39  xorps   xmm0, xmm0
0x18005ad3c  movups  xmmword ptr [rax], xmm0
0x18005ad3f  mov     dword ptr [rax+8], 1
0x18005ad46  mov     dword ptr [rax+0Ch], 1
0x18005ad4d  lea     rcx, ??_7?$_Ref_count_resource@PEAUHINSTANCE__@@V_lambda_6bfbb92090c379a9aabfb7129ba6d39d_@@@std@@6B@; const std::_Ref_count_resource<HINSTANCE__ *,_lambda_6bfbb92090c379a9aabfb7129ba6d39d_>::`vftable'
0x18005ad54  mov     [rax], rcx
0x18005ad57  mov     [rax+10h], rbx
0x18005ad5b  mov     [rdi+8], rbx
0x18005ad5f  mov     rbx, [rdi+10h]
0x18005ad63  mov     [rdi+10h], rax
0x18005ad67  test    rbx, rbx
0x18005ad6a  jz      short loc_18005ADA3
0x18005ad6c  or      esi, 0FFFFFFFFh
0x18005ad6f  mov     eax, esi
0x18005ad71  lock xadd [rbx+8], eax
0x18005ad76  add     eax, esi
0x18005ad78  jnz     short loc_18005ADA3
0x18005ad7a  mov     rax, [rbx]
0x18005ad7d  mov     rcx, rbx
0x18005ad80  mov     rax, [rax]
0x18005ad83  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005ad88  mov     eax, esi
0x18005ad8a  lock xadd [rbx+0Ch], eax
0x18005ad8f  add     eax, esi
0x18005ad91  jnz     short loc_18005ADA3
0x18005ad93  mov     rax, [rbx]
0x18005ad96  mov     rcx, rbx
0x18005ad99  mov     rax, [rax+8]
0x18005ad9d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005ada2  nop
0x18005ada3  mov     rax, rdi
0x18005ada6  lea     r11, [rsp+68h+var_8]
0x18005adab  mov     rbx, [r11+18h]
0x18005adaf  mov     rsi, [r11+28h]
0x18005adb3  mov     rsp, r11
0x18005adb6  pop     rdi
0x18005adb7  retn
0x18005adb8  call    cs:__imp_GetLastError
0x18005adbe  nop
0x18005adbf  mov     ebx, eax
0x18005adc1  test    eax, eax
0x18005adc3  jle     short loc_18005ADCE
0x18005adc5  movzx   ebx, ax
0x18005adc8  or      ebx, 80070000h
0x18005adce  lea     rax, WPP_GLOBAL_Control
0x18005add5  mov     rdx, cs:WPP_GLOBAL_Control
0x18005addc  cmp     rdx, rax
0x18005addf  jz      short loc_18005AE07
0x18005ade1  test    byte ptr [rdx+1Ch], 1
0x18005ade5  jz      short loc_18005AE07
0x18005ade7  mov     rcx, rsi
0x18005adea  call    ?data@?$array@G$0BA@@std@@QEAAPEAGXZ; std::array<ushort,16>::data(void)
0x18005adef  mov     rcx, rax
0x18005adf2  call    ?c_str@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAPEBGXZ; std::wstring::c_str(void)
0x18005adf7  mov     [rsp+68h+var_40], ebx
0x18005adfb  mov     r9, rax
0x18005adfe  mov     rcx, [rdx+10h]
0x18005ae02  call    WPP_SF_Sld
0x18005ae07  mov     edx, ebx; int
0x18005ae09  lea     rcx, [rsp+68h+pExceptionObject]; this
0x18005ae0e  call    ??0ErrorCodeException@@QEAA@J@Z; ErrorCodeException::ErrorCodeException(long)
0x18005ae13  lea     rdx, _TI2?AVErrorCodeException@@; pThrowInfo
0x18005ae1a  lea     rcx, [rsp+68h+pExceptionObject]; pExceptionObject
0x18005ae1f  call    _CxxThrowException_0
```
