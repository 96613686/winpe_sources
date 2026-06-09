# DismMountClass::Mount(ushort const *,bool,ushort const *)

- ea: `0x180041734`
- end: `0x180041a18`
- name: `?Mount@DismMountClass@@QEAAJPEBG_N0@Z`
- size: `740`
- prototype: `__int64 __fastcall(DismMountClass *__hidden this, const unsigned __int16 *, bool, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `12`
- tags: ``

## callers

- `0x180042b6c`

## callees

- `0x1800059fc`
- `0x18000c6f0`
- `0x18001de7c`
- `0x18001ee18`
- `0x18001f0c0`
- `0x18001f218`
- `0x18001f47c`
- `0x1800412b8`
- `0x1800413d8`
- `0x180041734`
- `0x180041bf8`
- `0x18005cf30`

## import_xrefs

- `KERNEL32!CreateDirectoryW` at `0x180041950`
- `KERNEL32!CreateDirectoryW` at `0x180041950`
- `ole32!CoCreateGuid` at `0x180041840`
- `ole32!CoCreateGuid` at `0x180041840`
- `DismApi!DismMountImage` at `0x1800419c8`
- `DismApi!DismMountImage` at `0x1800419c8`

## string_xrefs

- `0x1800417c1`: `DismMountClass::Mount The class has already mounted a wim`
- `0x1800417e5`: `DismMountClass::Mount Mount directory: `
- `0x180041886`: `DismMountClass::Mount SecureGetTempPathW error 0x%x`
- `0x18004184c`: `DismMountClass::Mount CoCreateGuid error 0x%x`
- `0x180041920`: `DismMountClass::Mount StringCchPrintf error 0x%x`
- `0x180041965`: `DismMountClass::Mount CreateDirectory error %ls`
- `0x180041984`: `DismMountClass::Mount Mounting %ls to %ls`
- `0x1800419d4`: `DismMountClass::Mount DismMountImage error 0x%x`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall DismMountClass::Mount(
        DismMountClass *this,
        const unsigned __int16 *a2,
        char a3,
        unsigned __int16 *a4)
{
  unsigned int v7; // ebx
  _QWORD *v8; // rax
  const WCHAR *v9; // r9
  unsigned __int64 v10; // rax
  __int64 v11; // r9
  HRESULT v12; // eax
  int v13; // eax
  unsigned __int64 v14; // rax
  __int64 v15; // rcx
  const WCHAR *v16; // rax
  BOOL DirectoryW; // eax
  _QWORD *v18; // rcx
  _QWORD *v19; // rax
  _QWORD *v20; // rax
  _QWORD *v21; // rax
  int v22; // eax
  int Data2; // [rsp+20h] [rbp-89h]
  int Data3; // [rsp+28h] [rbp-81h]
  int v26; // [rsp+30h] [rbp-79h]
  int v27; // [rsp+38h] [rbp-71h]
  int v28; // [rsp+40h] [rbp-69h]
  int v29; // [rsp+48h] [rbp-61h]
  int v30; // [rsp+50h] [rbp-59h]
  int v31; // [rsp+58h] [rbp-51h]
  int v32; // [rsp+60h] [rbp-49h]
  int v33; // [rsp+68h] [rbp-41h]
  __int16 v34; // [rsp+70h] [rbp-39h] BYREF
  unsigned __int16 *v35[3]; // [rsp+78h] [rbp-31h] BYREF
  const unsigned __int16 *v36; // [rsp+90h] [rbp-19h]
  unsigned __int16 *v37[4]; // [rsp+98h] [rbp-11h] BYREF
  GUID pguid; // [rsp+B8h] [rbp+Fh] BYREF

  v37[3] = (unsigned __int16 *)-2LL;
  v36 = a2;
  *(_QWORD *)&pguid.Data1 = 0;
  *(_QWORD *)pguid.Data4 = 0;
  v34 = 0;
  std::_Vector_alloc<0,std::_Vec_base_types<unsigned short>>::_Vector_alloc<0,std::_Vec_base_types<unsigned short>>(v37);
  std::vector<unsigned short>::_Construct_n(v37, 260, &v34);
  v34 = 0;
  std::_Vector_alloc<0,std::_Vec_base_types<unsigned short>>::_Vector_alloc<0,std::_Vec_base_types<unsigned short>>(v35);
  std::vector<unsigned short>::_Construct_n(v35, 38, &v34);
  if ( *((_BYTE *)this + 41) )
  {
    v7 = -1052638937;
    UnattendLogW(1, L"DismMountClass::Mount The class has already mounted a wim");
  }
  else
  {
    *((_BYTE *)this + 40) = a3;
    if ( a4 )
    {
      UnattendLogW(0, L"DismMountClass::Mount Mount directory: ", a4);
    }
    else
    {
      a4 = v37[0];
      if ( !(unsigned int)SecureGetTempPathW(v37[1] - v37[0], v37[0]) )
      {
        UnattendLogW(2, L"DismMountClass::Mount SecureGetTempPathW error 0x%x", 0);
        v7 = -2147467259;
        goto LABEL_19;
      }
    }
    std::wstring::assign((char *)this + 8, a4);
    v8 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr((_QWORD *)this + 1);
    v9 = &cchOriginalDestLength;
    if ( *((_WORD *)v8 + *((_QWORD *)this + 3) - 1) != 92 )
      v9 = L"\\";
    v10 = std::char_traits<unsigned short>::length(v9);
    std::wstring::append((_QWORD *)this + 1, v11, v10);
    v12 = CoCreateGuid(&pguid);
    v7 = v12;
    if ( v12 >= 0 )
    {
      v33 = pguid.Data4[7];
      v32 = pguid.Data4[6];
      v31 = pguid.Data4[5];
      v30 = pguid.Data4[4];
      v29 = pguid.Data4[3];
      v28 = pguid.Data4[2];
      v27 = pguid.Data4[1];
      v26 = pguid.Data4[0];
      Data3 = pguid.Data3;
      Data2 = pguid.Data2;
      v13 = StringCchPrintfW(
              v35[0],
              v35[1] - v35[0],
              L"%08x-%04x-%04x-%02x%02x-%02x%02x%02x%02x%02x%02x",
              pguid.Data1,
              Data2,
              Data3,
              v26,
              v27,
              v28,
              v29,
              v30,
              v31,
              v32,
              v33);
      v7 = v13;
      if ( v13 >= 0 )
      {
        v14 = std::char_traits<unsigned short>::length(v35[0]);
        std::wstring::append((_QWORD *)this + 1, v15, v14);
        v16 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr((_QWORD *)this + 1);
        DirectoryW = CreateDirectoryW(v16, 0);
        v18 = (_QWORD *)((char *)this + 8);
        if ( DirectoryW )
        {
          v20 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v18);
          UnattendLogW(0, L"DismMountClass::Mount Mounting %ls to %ls", v36, v20);
          v21 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr((_QWORD *)this + 1);
          v22 = DismMountImage(v36, v21, 1);
          v7 = v22;
          if ( v22 >= 0 )
            *((_BYTE *)this + 41) = 1;
          else
            UnattendLogW(2, L"DismMountClass::Mount DismMountImage error 0x%x", (unsigned int)v22);
        }
        else
        {
          v19 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v18);
          UnattendLogW(2, L"DismMountClass::Mount CreateDirectory error %ls", v19);
        }
      }
      else
      {
        UnattendLogW(2, L"DismMountClass::Mount StringCchPrintf error 0x%x", (unsigned int)v13);
      }
    }
    else
    {
      UnattendLogW(2, L"DismMountClass::Mount CoCreateGuid error 0x%x", (unsigned int)v12);
    }
  }
LABEL_19:
  std::vector<unsigned short>::~vector<unsigned short>(v35);
  std::vector<unsigned short>::~vector<unsigned short>(v37);
  return v7;
}

```

## disassembly

```asm
0x180041734  push    rbp
0x180041736  push    rbx
0x180041737  push    rsi
0x180041738  push    rdi
0x180041739  push    r13
0x18004173b  push    r14
0x18004173d  push    r15
0x18004173f  lea     rbp, [rsp-27h]
0x180041744  sub     rsp, 0D0h
0x18004174b  mov     [rbp+57h+var_50], 0FFFFFFFFFFFFFFFEh
0x180041753  mov     rax, cs:__security_cookie
0x18004175a  xor     rax, rsp
0x18004175d  mov     [rbp+57h+var_38], rax
0x180041761  mov     rbx, r9
0x180041764  mov     dil, r8b
0x180041767  mov     [rbp+57h+var_70], rdx
0x18004176b  mov     r13, rcx
0x18004176e  xor     esi, esi
0x180041770  mov     qword ptr [rbp+57h+pguid.Data1], rsi
0x180041774  mov     qword ptr [rbp+57h+pguid.Data4], rsi
0x180041778  mov     [rbp+57h+var_90], si
0x18004177c  lea     rcx, [rbp+57h+var_68]
0x180041780  call    ??0?$_Vector_alloc@$0A@U?$_Vec_base_types@GV?$allocator@G@std@@@std@@@std@@QEAA@AEBV?$allocator@G@1@@Z; std::_Vector_alloc<0,std::_Vec_base_types<ushort>>::_Vector_alloc<0,std::_Vec_base_types<ushort>>(std::allocator<ushort> const &)
0x180041785  lea     r8, [rbp+57h+var_90]
0x180041789  mov     edx, 104h
0x18004178e  lea     rcx, [rbp+57h+var_68]
0x180041792  call    ?_Construct_n@?$vector@GV?$allocator@G@std@@@std@@QEAAX_KPEBG@Z; std::vector<ushort>::_Construct_n(unsigned __int64,ushort const *)
0x180041797  nop
0x180041798  mov     [rbp+57h+var_90], si
0x18004179c  lea     rcx, [rbp+57h+var_88]
0x1800417a0  call    ??0?$_Vector_alloc@$0A@U?$_Vec_base_types@GV?$allocator@G@std@@@std@@@std@@QEAA@AEBV?$allocator@G@1@@Z; std::_Vector_alloc<0,std::_Vec_base_types<ushort>>::_Vector_alloc<0,std::_Vec_base_types<ushort>>(std::allocator<ushort> const &)
0x1800417a5  lea     r8, [rbp+57h+var_90]
0x1800417a9  lea     edx, [rsi+26h]
0x1800417ac  lea     rcx, [rbp+57h+var_88]
0x1800417b0  call    ?_Construct_n@?$vector@GV?$allocator@G@std@@@std@@QEAAX_KPEBG@Z; std::vector<ushort>::_Construct_n(unsigned __int64,ushort const *)
0x1800417b5  nop
0x1800417b6  cmp     [r13+29h], sil
0x1800417ba  jz      short loc_1800417D5
0x1800417bc  mov     ebx, 0C1420127h
0x1800417c1  lea     rdx, aDismmountclass_8; "DismMountClass::Mount The class has alr"...
0x1800417c8  lea     ecx, [rsi+1]
0x1800417cb  call    UnattendLogW
0x1800417d0  jmp     loc_1800419E5
0x1800417d5  mov     [r13+28h], dil
0x1800417d9  test    rbx, rbx
0x1800417dc  jz      loc_180041865
0x1800417e2  mov     r8, rbx
0x1800417e5  lea     rdx, aDismmountclass_3; "DismMountClass::Mount Mount directory: "
0x1800417ec  xor     ecx, ecx
0x1800417ee  call    UnattendLogW
0x1800417f3  lea     r15, [r13+8]
0x1800417f7  mov     rdx, rbx
0x1800417fa  mov     rcx, r15
0x1800417fd  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z; std::wstring::assign(ushort const *)
0x180041802  mov     rcx, r15
0x180041805  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18004180a  mov     rcx, [r13+18h]
0x18004180e  lea     rdx, pszSrc; "\\"
0x180041815  lea     r9, cchOriginalDestLength
0x18004181c  cmp     word ptr [rax+rcx*2-2], 5Ch ; '\'
0x180041822  cmovnz  r9, rdx
0x180041826  mov     rcx, r9
0x180041829  call    ?length@?$char_traits@G@std@@SA_KPEBG@Z; std::char_traits<ushort>::length(ushort const *)
0x18004182e  mov     r8, rax
0x180041831  mov     rdx, r9
0x180041834  mov     rcx, r15
0x180041837  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::append(ushort const *,unsigned __int64)
0x18004183c  lea     rcx, [rbp+57h+pguid]; pguid
0x180041840  call    cs:__imp_CoCreateGuid
0x180041846  mov     ebx, eax
0x180041848  test    eax, eax
0x18004184a  jns     short loc_18004189F
0x18004184c  lea     rdx, aDismmountclass_0; "DismMountClass::Mount CoCreateGuid erro"...
0x180041853  mov     r8d, eax
0x180041856  mov     ecx, 2
0x18004185b  call    UnattendLogW
0x180041860  jmp     loc_1800419E5
0x180041865  mov     rcx, [rbp+57h+var_60]
0x180041869  mov     rbx, [rbp+57h+var_68]
0x18004186d  sub     rcx, rbx
0x180041870  sar     rcx, 1; unsigned int
0x180041873  mov     rdx, rbx; unsigned __int16 *
0x180041876  call    ?SecureGetTempPathW@@YAKKPEAG@Z; SecureGetTempPathW(ulong,ushort *)
0x18004187b  test    eax, eax
0x18004187d  jnz     loc_1800417F3
0x180041883  xor     r8d, r8d
0x180041886  lea     rdx, aDismmountclass_12; "DismMountClass::Mount SecureGetTempPath"...
0x18004188d  lea     ecx, [rax+2]
0x180041890  call    UnattendLogW
0x180041895  mov     ebx, 80004005h
0x18004189a  jmp     loc_1800419E5
0x18004189f  movzx   eax, [rbp+57h+pguid.Data4+7]
0x1800418a3  movzx   ecx, [rbp+57h+pguid.Data4+6]
0x1800418a7  movzx   r8d, [rbp+57h+pguid.Data4+5]
0x1800418ac  movzx   r9d, [rbp+57h+pguid.Data4+4]
0x1800418b1  movzx   r10d, [rbp+57h+pguid.Data4+3]
0x1800418b6  movzx   r11d, [rbp+57h+pguid.Data4+2]
0x1800418bb  movzx   ebx, [rbp+57h+pguid.Data4+1]
0x1800418bf  movzx   edi, [rbp+57h+pguid.Data4]
0x1800418c3  movzx   esi, [rbp+57h+pguid.Data3]
0x1800418c7  movzx   r14d, [rbp+57h+pguid.Data2]
0x1800418cc  mov     rdx, [rbp+57h+var_80]
0x1800418d0  sub     rdx, [rbp+57h+var_88]
0x1800418d4  sar     rdx, 1; unsigned __int64
0x1800418d7  mov     [rsp+100h+var_98], eax
0x1800418db  mov     [rsp+100h+var_A0], ecx
0x1800418df  mov     [rsp+100h+var_A8], r8d
0x1800418e4  mov     [rsp+100h+var_B0], r9d
0x1800418e9  mov     [rsp+100h+var_B8], r10d
0x1800418ee  mov     dword ptr [rsp+100h+var_C0], r11d
0x1800418f3  mov     dword ptr [rsp+100h+var_C8], ebx
0x1800418f7  mov     dword ptr [rsp+100h+var_D0], edi
0x1800418fb  mov     [rsp+100h+var_D8], esi
0x1800418ff  mov     [rsp+100h+var_E0], r14d
0x180041904  mov     r9d, [rbp+57h+pguid.Data1]
0x180041908  lea     r8, a08x04x04x02x02; "%08x-%04x-%04x-%02x%02x-%02x%02x%02x%02"...
0x18004190f  mov     rcx, [rbp+57h+var_88]; unsigned __int16 *
0x180041913  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180041918  mov     ebx, eax
0x18004191a  xor     edi, edi
0x18004191c  test    eax, eax
0x18004191e  jns     short loc_18004192C
0x180041920  lea     rdx, aDismmountclass_2; "DismMountClass::Mount StringCchPrintf e"...
0x180041927  jmp     loc_180041853
0x18004192c  mov     rcx, [rbp+57h+var_88]
0x180041930  call    ?length@?$char_traits@G@std@@SA_KPEBG@Z; std::char_traits<ushort>::length(ushort const *)
0x180041935  mov     r8, rax
0x180041938  mov     rdx, rcx
0x18004193b  mov     rcx, r15
0x18004193e  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::append(ushort const *,unsigned __int64)
0x180041943  mov     rcx, r15
0x180041946  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18004194b  xor     edx, edx; lpSecurityAttributes
0x18004194d  mov     rcx, rax; lpPathName
0x180041950  call    cs:__imp_CreateDirectoryW
0x180041956  mov     rcx, r15
0x180041959  test    eax, eax
0x18004195b  jnz     short loc_180041978
0x18004195d  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180041962  mov     r8, rax
0x180041965  lea     rdx, aDismmountclass_7; "DismMountClass::Mount CreateDirectory e"...
0x18004196c  mov     ecx, 2
0x180041971  call    UnattendLogW
0x180041976  jmp     short loc_1800419E5
0x180041978  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18004197d  mov     r9, rax
0x180041980  mov     r8, [rbp+57h+var_70]
0x180041984  lea     rdx, aDismmountclass_1; "DismMountClass::Mount Mounting %ls to %"...
0x18004198b  xor     ecx, ecx
0x18004198d  call    UnattendLogW
0x180041992  mov     rcx, r15
0x180041995  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18004199a  mov     edx, edi
0x18004199c  cmp     [r13+28h], dil
0x1800419a0  setnz   dl
0x1800419a3  mov     [rsp+100h+var_C0], rdi
0x1800419a8  mov     [rsp+100h+var_C8], rdi
0x1800419ad  mov     [rsp+100h+var_D0], rdi
0x1800419b2  mov     [rsp+100h+var_D8], edx
0x1800419b6  mov     [rsp+100h+var_E0], edi
0x1800419ba  xor     r9d, r9d
0x1800419bd  lea     r8d, [r9+1]
0x1800419c1  mov     rdx, rax
0x1800419c4  mov     rcx, [rbp+57h+var_70]
0x1800419c8  call    cs:__imp_DismMountImage
0x1800419ce  mov     ebx, eax
0x1800419d0  test    eax, eax
0x1800419d2  jns     short loc_1800419E0
0x1800419d4  lea     rdx, aDismmountclass_13; "DismMountClass::Mount DismMountImage er"...
0x1800419db  jmp     loc_180041853
0x1800419e0  mov     byte ptr [r13+29h], 1
0x1800419e5  lea     rcx, [rbp+57h+var_88]
0x1800419e9  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x1800419ee  nop
0x1800419ef  lea     rcx, [rbp+57h+var_68]
0x1800419f3  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x1800419f8  mov     eax, ebx
0x1800419fa  mov     rcx, [rbp+57h+var_38]
0x1800419fe  xor     rcx, rsp; StackCookie
0x180041a01  call    __security_check_cookie
0x180041a06  add     rsp, 0D0h
0x180041a0d  pop     r15
0x180041a0f  pop     r14
0x180041a11  pop     r13
0x180041a13  pop     rdi
0x180041a14  pop     rsi
0x180041a15  pop     rbx
0x180041a16  pop     rbp
0x180041a17  retn
```
