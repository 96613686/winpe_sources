# CommonUtil::UtilGetModuleVersion(unsigned __int64 *,wchar_t const *)

- ea: `0x140003414`
- end: `0x140003559`
- name: `?UtilGetModuleVersion@CommonUtil@@YAJPEA_KPEB_W@Z`
- size: `325`
- prototype: `__int64 __fastcall(CommonUtil *__hidden this, unsigned __int64 *, const wchar_t *)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, broker_com_uri`

## callers

- `0x14001d464`

## callees

- `0x140003380`
- `0x140003414`
- `0x14000355c`
- `0x1400037a4`
- `0x140003a24`
- `0x140005c20`
- `0x140005c40`

## pseudocode

```c
int __fastcall CommonUtil::UtilGetModuleVersion(CommonUtil *this, HINSTANCE *a2, const wchar_t *a3)
{
  int result; // eax
  HINSTANCE v5; // r8
  HINSTANCE v6; // r9
  int ModuleFileName; // ebx
  const unsigned __int8 *v8; // r8
  int FileVersion; // edi
  _OWORD v10[3]; // [rsp+28h] [rbp-58h] BYREF
  int v11; // [rsp+58h] [rbp-28h]
  wchar_t **v12; // [rsp+60h] [rbp-20h] BYREF
  void *v13; // [rsp+68h] [rbp-18h] BYREF

  v12 = 0;
  result = CommonUtil::HrGetModuleHandle((CommonUtil *)&v12, a2, a3);
  if ( result >= 0 )
  {
    v13 = 0;
    ModuleFileName = CommonUtil::UtilGetModuleFileName((CommonUtil *)&v13, v12, v5, v6);
    if ( ModuleFileName < 0
      || (ModuleFileName = CommonUtil::UtilGetVersionInfoInternal((CommonUtil *)1), ModuleFileName < 0) )
    {
      if ( v13 )
        operator delete(v13);
      return ModuleFileName;
    }
    else
    {
      v11 = 0;
      memset(v10, 0, sizeof(v10));
      FileVersion = CommonUtil::UtilGetFileVersion((CommonUtil *)v10, 0, v8);
      if ( FileVersion >= 0 )
      {
        *(_QWORD *)this = HIDWORD(v10[0]) + ((unsigned __int64)DWORD2(v10[0]) << 32);
        if ( v13 )
          operator delete(v13);
        return 0;
      }
      else
      {
        if ( v13 )
          operator delete(v13);
        return FileVersion;
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x140003414  mov     [rsp-18h+arg_10], rbx
0x140003419  push    rbp
0x14000341a  push    rsi
0x14000341b  push    rdi
0x14000341c  mov     rbp, rsp
0x14000341f  sub     rsp, 80h
0x140003426  mov     rax, cs:__security_cookie
0x14000342d  xor     rax, rsp
0x140003430  mov     [rbp+var_10], rax
0x140003434  mov     rsi, rcx
0x140003437  mov     [rbp+var_20], 0
0x14000343f  lea     rcx, [rbp+var_20]; this
0x140003443  call    ?HrGetModuleHandle@CommonUtil@@YAJPEAPEAUHINSTANCE__@@PEB_W@Z; CommonUtil::HrGetModuleHandle(HINSTANCE__ * *,wchar_t const *)
0x140003448  mov     edx, eax
0x14000344a  shr     edx, 1Fh
0x14000344d  test    dl, dl
0x14000344f  jnz     loc_14000353A
0x140003455  mov     rdx, [rbp+var_20]; wchar_t **
0x140003459  lea     rcx, [rbp+var_18]; this
0x14000345d  mov     [rbp+var_18], 0
0x140003465  call    ?UtilGetModuleFileName@CommonUtil@@YAJPEAPEA_WPEAUHINSTANCE__@@@Z; CommonUtil::UtilGetModuleFileName(wchar_t * *,HINSTANCE__ *)
0x14000346a  mov     ecx, eax
0x14000346c  mov     ebx, eax
0x14000346e  shr     ecx, 1Fh
0x140003471  test    cl, cl
0x140003473  jz      short loc_14000348A
0x140003475  mov     rcx, [rbp+var_18]; void *
0x140003479  test    rcx, rcx
0x14000347c  jz      short loc_140003483
0x14000347e  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x140003483  mov     eax, ebx
0x140003485  jmp     loc_14000353A
0x14000348a  mov     r8, [rbp+var_18]
0x14000348e  lea     rdx, [rbp+var_60]
0x140003492  mov     ecx, 1; this
0x140003497  mov     [rbp+var_60], 0
0x14000349f  call    CommonUtil__UtilGetVersionInfoInternal
0x1400034a4  mov     ecx, eax
0x1400034a6  mov     ebx, eax
0x1400034a8  shr     ecx, 1Fh
0x1400034ab  test    cl, cl
0x1400034ad  jz      short loc_1400034BF
0x1400034af  mov     rcx, [rbp+var_60]; void *
0x1400034b3  test    rcx, rcx
0x1400034b6  jz      short loc_140003475
0x1400034b8  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1400034bd  jmp     short loc_140003475
0x1400034bf  mov     rbx, [rbp+var_60]
0x1400034c3  lea     rcx, [rbp+var_58]; this
0x1400034c7  xorps   xmm0, xmm0
0x1400034ca  xor     eax, eax
0x1400034cc  mov     rdx, rbx; struct tagVS_FIXEDFILEINFO *
0x1400034cf  mov     [rbp+var_28], eax
0x1400034d2  movups  [rbp+var_58], xmm0
0x1400034d6  movups  [rbp+var_48], xmm0
0x1400034da  movups  [rbp+var_38], xmm0
0x1400034de  call    ?UtilGetFileVersion@CommonUtil@@YAJPEAUtagVS_FIXEDFILEINFO@@PEBE@Z; CommonUtil::UtilGetFileVersion(tagVS_FIXEDFILEINFO *,uchar const *)
0x1400034e3  mov     ecx, eax
0x1400034e5  mov     edi, eax
0x1400034e7  shr     ecx, 1Fh
0x1400034ea  test    cl, cl
0x1400034ec  jz      short loc_14000350D
0x1400034ee  test    rbx, rbx
0x1400034f1  jz      short loc_1400034FB
0x1400034f3  mov     rcx, rbx; void *
0x1400034f6  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1400034fb  mov     rcx, [rbp+var_18]; void *
0x1400034ff  test    rcx, rcx
0x140003502  jz      short loc_140003509
0x140003504  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x140003509  mov     eax, edi
0x14000350b  jmp     short loc_14000353A
0x14000350d  mov     ecx, dword ptr [rbp+var_58+8]
0x140003510  mov     eax, dword ptr [rbp+var_58+0Ch]
0x140003513  shl     rcx, 20h
0x140003517  add     rcx, rax
0x14000351a  mov     [rsi], rcx
0x14000351d  test    rbx, rbx
0x140003520  jz      short loc_14000352A
0x140003522  mov     rcx, rbx; void *
0x140003525  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x14000352a  mov     rcx, [rbp+var_18]; void *
0x14000352e  test    rcx, rcx
0x140003531  jz      short loc_140003538
0x140003533  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x140003538  xor     eax, eax
0x14000353a  mov     rcx, [rbp+var_10]
0x14000353e  xor     rcx, rsp; StackCookie
0x140003541  call    __security_check_cookie
0x140003546  mov     rbx, [rsp+80h+arg_10]
0x14000354e  add     rsp, 80h
0x140003555  pop     rdi
0x140003556  pop     rsi
0x140003557  pop     rbp
0x140003558  retn
```
