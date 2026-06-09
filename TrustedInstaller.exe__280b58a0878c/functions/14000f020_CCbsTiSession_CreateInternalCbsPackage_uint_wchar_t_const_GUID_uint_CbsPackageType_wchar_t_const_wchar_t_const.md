# CCbsTiSession::CreateInternalCbsPackage(uint,wchar_t const *,_GUID,uint,_CbsPackageType,wchar_t const *,wchar_t const *,uint,tagCbsPackageDecryptionData * const,tagCBS_PACKAGE_ENCRYPTION_ENUM,ICbsPackage * *)

- ea: `0x14000f020`
- end: `0x14000f1b2`
- name: `?CreateInternalCbsPackage@CCbsTiSession@@QEAAJIPEB_WU_GUID@@IW4_CbsPackageType@@00IQEAUtagCbsPackageDecryptionData@@W4tagCBS_PACKAGE_ENCRYPTION_ENUM@@PEAPEAUICbsPackage@@@Z`
- size: `402`
- prototype: `__int64 __fastcall(CCbsTiSession *, unsigned int, __int64, __int128 *, int, int, __int64, __int64, int, __int64, int, __int64)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x14000f238`
- `0x140013414`

## callees

- `0x1400023e0`
- `0x14000f020`
- `0x1400106c4`
- `0x140017658`
- `0x14002b010`

## string_xrefs

- `0x14000f148`: `Failed to CreatePackage using worker session`

## pseudocode

```c
__int64 __fastcall CCbsTiSession::CreateInternalCbsPackage(
        CCbsTiSession *a1,
        unsigned int a2,
        __int64 a3,
        __int128 *a4,
        int a5,
        int a6,
        __int64 a7,
        __int64 a8,
        int a9,
        __int64 a10,
        int a11,
        __int64 a12)
{
  unsigned int v16; // ebx
  const char *v17; // r9
  __int64 v18; // rdx
  int SureWorkerSessionAvailable; // eax
  __int64 v20; // rcx
  __int64 (__fastcall *v21)(__int64, _QWORD, __int64, __int128 *, int, int, __int64, __int64, int, __int64, int, __int64 *); // rax
  __int128 v23; // [rsp+80h] [rbp-68h] BYREF
  __int64 v24; // [rsp+90h] [rbp-58h] BYREF

  v24 = 0;
  if ( !a12 )
  {
    v16 = -2147467261;
    v17 = "Invalid argument: ppPackage.";
    v18 = 2147500035LL;
LABEL_3:
    CBSWdsLogLight(0x4000000, v18, 1, v17);
    goto LABEL_10;
  }
  SureWorkerSessionAvailable = CCbsTiSession::MakeSureWorkerSessionAvailable(a1, 1);
  v16 = SureWorkerSessionAvailable;
  if ( SureWorkerSessionAvailable < 0 )
  {
    v17 = "Failed to get worker session.";
LABEL_6:
    v18 = (unsigned int)SureWorkerSessionAvailable;
    goto LABEL_3;
  }
  v20 = *((_QWORD *)a1 + 5);
  v21 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64, __int128 *, int, int, __int64, __int64, int, __int64, int, __int64 *))(*(_QWORD *)v20 + 136LL);
  v23 = *a4;
  SureWorkerSessionAvailable = v21(v20, a2, a3, &v23, a5, a6, a7, a8, a9, a10, a11, &v24);
  v16 = SureWorkerSessionAvailable;
  if ( SureWorkerSessionAvailable < 0 )
  {
    v17 = "Failed to CreatePackage using worker session";
    goto LABEL_6;
  }
  v16 = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64))v24)(
          v24,
          &GUID_75207393_23f2_4396_85f0_8fdb879ed0ed,
          a12);
LABEL_10:
  if ( v24 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
  return v16;
}

```

## disassembly

```asm
0x14000f020  mov     r11, rsp
0x14000f023  push    rbx
0x14000f024  push    rbp
0x14000f025  push    rsi
0x14000f026  push    rdi
0x14000f027  push    r12
0x14000f029  push    r13
0x14000f02b  push    r14
0x14000f02d  push    r15
0x14000f02f  sub     rsp, 0A8h
0x14000f036  mov     rax, cs:__security_cookie
0x14000f03d  xor     rax, rsp
0x14000f040  mov     [rsp+0E8h+var_50], rax
0x14000f048  mov     rax, [rsp+0E8h+arg_48]
0x14000f050  mov     r15, r9
0x14000f053  mov     r12, [rsp+0E8h+arg_30]
0x14000f05b  mov     r14, r8
0x14000f05e  mov     r13, [rsp+0E8h+arg_38]
0x14000f066  mov     ebp, edx
0x14000f068  mov     rdi, [rsp+0E8h+arg_58]
0x14000f070  mov     rsi, rcx
0x14000f073  mov     [rsp+0E8h+var_78], rax
0x14000f078  mov     qword ptr [r11-58h], 0
0x14000f080  test    rdi, rdi
0x14000f083  jnz     short loc_14000F0A8
0x14000f085  mov     ebx, 80004003h
0x14000f08a  lea     r9, aInvalidArgumen_26; "Invalid argument: ppPackage."
0x14000f091  mov     edx, ebx
0x14000f093  mov     r8d, 1
0x14000f099  mov     ecx, 4000000h
0x14000f09e  call    ?CBSWdsLogLight@@YAXW4tagLOG_SETUPLOG_SEVERITY@@J_NPEBDZZ; CBSWdsLogLight(tagLOG_SETUPLOG_SEVERITY,long,bool,char const *,...)
0x14000f0a3  jmp     loc_14000F173
0x14000f0a8  mov     dl, 1; bool
0x14000f0aa  call    ?MakeSureWorkerSessionAvailable@CCbsTiSession@@QEAAJ_N@Z; CCbsTiSession::MakeSureWorkerSessionAvailable(bool)
0x14000f0af  mov     ebx, eax
0x14000f0b1  test    eax, eax
0x14000f0b3  jns     short loc_14000F0C0
0x14000f0b5  lea     r9, aFailedToGetWor_1; "Failed to get worker session."
0x14000f0bc  mov     edx, eax
0x14000f0be  jmp     short loc_14000F093
0x14000f0c0  mov     r9d, [rsp+0E8h+arg_50]
0x14000f0c8  lea     rdx, [rsp+0E8h+var_58]
0x14000f0d0  mov     rcx, [rsi+28h]
0x14000f0d4  mov     r8, r14
0x14000f0d7  movaps  xmm0, xmmword ptr [r15]
0x14000f0db  mov     [rsp+0E8h+var_90], rdx
0x14000f0e0  mov     rdx, [rsp+0E8h+var_78]
0x14000f0e5  mov     rax, [rcx]
0x14000f0e8  mov     [rsp+0E8h+var_98], r9d
0x14000f0ed  mov     r9d, [rsp+0E8h+arg_40]
0x14000f0f5  mov     [rsp+0E8h+var_A0], rdx
0x14000f0fa  mov     edx, ebp
0x14000f0fc  mov     rax, [rax+88h]
0x14000f103  mov     [rsp+0E8h+var_A8], r9d
0x14000f108  mov     r9d, [rsp+0E8h+arg_28]
0x14000f110  mov     [rsp+0E8h+var_B0], r13
0x14000f115  mov     [rsp+0E8h+var_B8], r12
0x14000f11a  mov     [rsp+0E8h+var_C0], r9d
0x14000f11f  mov     r9d, [rsp+0E8h+arg_20]
0x14000f127  mov     [rsp+0E8h+var_C8], r9d
0x14000f12c  lea     r9, [rsp+0E8h+var_68]
0x14000f134  movdqa  [rsp+0E8h+var_68], xmm0
0x14000f13d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000f142  mov     ebx, eax
0x14000f144  test    eax, eax
0x14000f146  jns     short loc_14000F154
0x14000f148  lea     r9, aFailedToCreate_21; "Failed to CreatePackage using worker se"...
0x14000f14f  jmp     loc_14000F0BC
0x14000f154  mov     rcx, [rsp+0E8h+var_58]
0x14000f15c  lea     rdx, _GUID_75207393_23f2_4396_85f0_8fdb879ed0ed
0x14000f163  mov     r8, rdi
0x14000f166  mov     rax, [rcx]
0x14000f169  mov     rax, [rax]
0x14000f16c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000f171  mov     ebx, eax
0x14000f173  mov     rcx, [rsp+0E8h+var_58]
0x14000f17b  test    rcx, rcx
0x14000f17e  jz      short loc_14000F18C
0x14000f180  mov     rax, [rcx]
0x14000f183  mov     rax, [rax+10h]
0x14000f187  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000f18c  mov     eax, ebx
0x14000f18e  mov     rcx, [rsp+0E8h+var_50]
0x14000f196  xor     rcx, rsp; StackCookie
0x14000f199  call    __security_check_cookie
0x14000f19e  add     rsp, 0A8h
0x14000f1a5  pop     r15
0x14000f1a7  pop     r14
0x14000f1a9  pop     r13
0x14000f1ab  pop     r12
0x14000f1ad  pop     rdi
0x14000f1ae  pop     rsi
0x14000f1af  pop     rbp
0x14000f1b0  pop     rbx
0x14000f1b1  retn
```
