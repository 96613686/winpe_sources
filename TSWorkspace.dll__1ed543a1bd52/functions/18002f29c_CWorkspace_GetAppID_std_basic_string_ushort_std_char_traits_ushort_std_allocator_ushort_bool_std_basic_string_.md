# CWorkspace::GetAppID(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,bool *,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x18002f29c`
- end: `0x18002f49b`
- name: `?GetAppID@CWorkspace@@QEAAXV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEA_NAEAV23@@Z`
- size: `511`
- prototype: `void __fastcall(__int64, void *, _BYTE *, __int64)`
- caller_count: `2`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x18002b1a8`
- `0x18002cab8`

## callees

- `0x180003108`
- `0x1800055d0`
- `0x18000b1d8`
- `0x18000d8d4`
- `0x18000dbdc`
- `0x18000ece0`
- `0x1800107e8`
- `0x18001082c`
- `0x18002f29c`
- `0x18009a520`

## import_xrefs

- `msvcrt!fclose` at `0x18002f46e`
- `msvcrt!fclose` at `0x18002f46e`
- `msvcrt!iswcntrl` at `0x18002f444`
- `msvcrt!iswcntrl` at `0x18002f444`
- `msvcrt!fgetws` at `0x18002f338`
- `msvcrt!fgetws` at `0x18002f338`
- `msvcrt!_wfopen_s` at `0x18002f318`
- `msvcrt!_wfopen_s` at `0x18002f318`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18002f367`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18002f367`

## string_xrefs

- `0x18002f3c6`: `StringCchCopy failed`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall CWorkspace::GetAppID(__int64 a1, void *a2, _BYTE *a3, __int64 a4)
{
  unsigned __int16 *v7; // rbx
  const wchar_t *v8; // rax
  int v9; // edi
  unsigned __int64 v10; // r11
  unsigned int CurrentThreadActivityIdPrefix; // eax
  int v12; // edx
  const char *v13; // rcx
  unsigned __int64 v14; // rdi
  __int64 cchCount2; // [rsp+28h] [rbp-860h]
  FILE *Stream; // [rsp+30h] [rbp-858h] BYREF
  unsigned __int64 v17[3]; // [rsp+38h] [rbp-850h] BYREF
  wchar_t Buffer[25]; // [rsp+50h] [rbp-838h] BYREF
  unsigned __int16 v19[999]; // [rsp+82h] [rbp-806h] BYREF

  v17[1] = -2;
  v17[2] = (unsigned __int64)a2;
  Stream = 0;
  v7 = (unsigned __int16 *)operator new[](0x208u, (const struct std::nothrow_t *)&std::nothrow);
  v17[0] = 0;
  *v7 = 0;
  *a3 = 0;
  v8 = (const wchar_t *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a2);
  if ( !_wfopen_s(&Stream, v8, L"r") )
  {
    do
    {
      if ( !fgetws(Buffer, 1024, Stream) )
        goto LABEL_18;
    }
    while ( CompareStringW(0x7Fu, 1u, L"RemoteApplicationAppID", 22, Buffer, 22) != 2 );
    v9 = StringCchCopyW(v7, 0x104u, v19);
    if ( v9 >= 0 )
    {
      v9 = StringCchLengthW(v7, v10, v17);
      if ( v9 >= 0 )
      {
        v14 = v17[0];
        if ( iswcntrl(v7[v17[0] - 1]) )
          v7[v14 - 1] = 0;
        *a3 = 1;
      }
      else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
             && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
             && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
        v12 = 259;
        v13 = "StringCchLength failed";
        goto LABEL_9;
      }
    }
    else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
           && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
           && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
      v12 = 258;
      v13 = "StringCchCopy failed";
LABEL_9:
      LODWORD(cchCount2) = v9;
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v12,
        (unsigned int)WPP_f0913c8960533a51b69146b4f6d8f653_Traceguids,
        CurrentThreadActivityIdPrefix,
        (__int64)v13,
        cchCount2);
    }
  }
LABEL_18:
  std::wstring::assign(a4, v7);
  if ( Stream )
    fclose(Stream);
  std::wstring::~wstring(a2);
}

```

## disassembly

```asm
0x18002f29c  push    rbx
0x18002f29e  push    rbp
0x18002f29f  push    rsi
0x18002f2a0  push    rdi
0x18002f2a1  push    r14
0x18002f2a3  sub     rsp, 860h
0x18002f2aa  mov     [rsp+888h+var_848], 0FFFFFFFFFFFFFFFEh
0x18002f2b3  mov     rax, cs:__security_cookie
0x18002f2ba  xor     rax, rsp
0x18002f2bd  mov     [rsp+888h+var_38], rax
0x18002f2c5  mov     rbp, r9
0x18002f2c8  mov     r14, r8
0x18002f2cb  mov     rsi, rdx
0x18002f2ce  mov     [rsp+888h+var_840], rdx
0x18002f2d3  mov     [rsp+888h+Stream], 0
0x18002f2dc  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18002f2e3  mov     ecx, 208h; unsigned __int64
0x18002f2e8  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18002f2ed  mov     rbx, rax
0x18002f2f0  mov     [rsp+888h+var_850], 0
0x18002f2f9  xor     ecx, ecx
0x18002f2fb  mov     [rax], cx
0x18002f2fe  mov     [r14], cl
0x18002f301  mov     rcx, rsi
0x18002f304  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18002f309  lea     r8, aR; "r"
0x18002f310  mov     rdx, rax; FileName
0x18002f313  lea     rcx, [rsp+888h+Stream]; Stream
0x18002f318  call    cs:__imp__wfopen_s
0x18002f31e  test    eax, eax
0x18002f320  jnz     loc_18002F459
0x18002f326  lea     edi, [rax+16h]
0x18002f329  mov     r8, [rsp+888h+Stream]; Stream
0x18002f32e  mov     edx, 400h; BufferCount
0x18002f333  lea     rcx, [rsp+888h+Buffer]; Buffer
0x18002f338  call    cs:__imp_fgetws
0x18002f33e  test    rax, rax
0x18002f341  jz      loc_18002F459
0x18002f347  mov     dword ptr [rsp+888h+cchCount2], edi; cchCount2
0x18002f34b  lea     rax, [rsp+888h+Buffer]
0x18002f350  mov     [rsp+888h+lpString2], rax; lpString2
0x18002f355  mov     r9d, edi; cchCount1
0x18002f358  lea     r8, String1; "RemoteApplicationAppID"
0x18002f35f  mov     edx, 1; dwCmpFlags
0x18002f364  lea     ecx, [rdx+7Eh]; Locale
0x18002f367  call    cs:__imp_CompareStringW
0x18002f36d  cmp     eax, 2
0x18002f370  jnz     short loc_18002F329
0x18002f372  lea     r8, [rsp+888h+var_806]; unsigned __int16 *
0x18002f37a  mov     r11d, 104h
0x18002f380  mov     edx, r11d; unsigned __int64
0x18002f383  mov     rcx, rbx; unsigned __int16 *
0x18002f386  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18002f38b  mov     edi, eax
0x18002f38d  test    eax, eax
0x18002f38f  jns     short loc_18002F3F2
0x18002f391  lea     rdx, WPP_GLOBAL_Control
0x18002f398  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f39f  cmp     rcx, rdx
0x18002f3a2  jz      loc_18002F459
0x18002f3a8  test    byte ptr [rcx+1Ch], 8
0x18002f3ac  jz      loc_18002F459
0x18002f3b2  cmp     byte ptr [rcx+19h], 2
0x18002f3b6  jb      loc_18002F459
0x18002f3bc  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18002f3c1  mov     edx, 102h
0x18002f3c6  lea     rcx, aStringcchcopyF_0; "StringCchCopy failed"
0x18002f3cd  mov     dword ptr [rsp+888h+cchCount2], edi
0x18002f3d1  mov     [rsp+888h+lpString2], rcx
0x18002f3d6  mov     r9d, eax
0x18002f3d9  lea     r8, WPP_f0913c8960533a51b69146b4f6d8f653_Traceguids
0x18002f3e0  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f3e7  mov     rcx, [rcx+10h]
0x18002f3eb  call    WPP_SF_DsD
0x18002f3f0  jmp     short loc_18002F459
0x18002f3f2  lea     r8, [rsp+888h+var_850]; unsigned __int64 *
0x18002f3f7  mov     rdx, r11; unsigned __int64
0x18002f3fa  mov     rcx, rbx; unsigned __int16 *
0x18002f3fd  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x18002f402  mov     edi, eax
0x18002f404  test    eax, eax
0x18002f406  jns     short loc_18002F43A
0x18002f408  lea     rdx, WPP_GLOBAL_Control
0x18002f40f  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f416  cmp     rcx, rdx
0x18002f419  jz      short loc_18002F459
0x18002f41b  test    byte ptr [rcx+1Ch], 8
0x18002f41f  jz      short loc_18002F459
0x18002f421  cmp     byte ptr [rcx+19h], 2
0x18002f425  jb      short loc_18002F459
0x18002f427  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18002f42c  mov     edx, 103h
0x18002f431  lea     rcx, aStringcchlengt_0; "StringCchLength failed"
0x18002f438  jmp     short loc_18002F3CD
0x18002f43a  mov     rdi, [rsp+888h+var_850]
0x18002f43f  movzx   ecx, word ptr [rbx+rdi*2-2]; C
0x18002f444  call    cs:__imp_iswcntrl
0x18002f44a  test    eax, eax
0x18002f44c  jz      short loc_18002F455
0x18002f44e  xor     eax, eax
0x18002f450  mov     [rbx+rdi*2-2], ax
0x18002f455  mov     byte ptr [r14], 1
0x18002f459  mov     rdx, rbx
0x18002f45c  mov     rcx, rbp
0x18002f45f  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z; std::wstring::assign(ushort const *)
0x18002f464  mov     rcx, [rsp+888h+Stream]; Stream
0x18002f469  test    rcx, rcx
0x18002f46c  jz      short loc_18002F475
0x18002f46e  call    cs:__imp_fclose
0x18002f474  nop
0x18002f475  mov     rcx, rsi; void *
0x18002f478  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002f47d  mov     rcx, [rsp+888h+var_38]
0x18002f485  xor     rcx, rsp; StackCookie
0x18002f488  call    __security_check_cookie
0x18002f48d  add     rsp, 860h
0x18002f494  pop     r14
0x18002f496  pop     rdi
0x18002f497  pop     rsi
0x18002f498  pop     rbp
0x18002f499  pop     rbx
0x18002f49a  retn
```
