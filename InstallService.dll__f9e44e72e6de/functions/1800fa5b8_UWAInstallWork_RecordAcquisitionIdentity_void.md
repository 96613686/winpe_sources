# UWAInstallWork::_RecordAcquisitionIdentity(void)

- ea: `0x1800fa5b8`
- end: `0x1800fa84e`
- name: `?_RecordAcquisitionIdentity@UWAInstallWork@@AEAAXXZ`
- size: `662`
- prototype: `void __fastcall(UWAInstallWork *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, installer_update`

## callers

- `0x1800f72e8`

## callees

- `0x18001c414`
- `0x1800fa5b8`
- `0x18011b84c`
- `0x1801ed8b8`
- `0x180215010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800fa5fe`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800fa60e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800fa61e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800fa683`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800fa799`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800fa81e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800fa829`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800fa834`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800fa5fe`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800fa60e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800fa61e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800fa683`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800fa799`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800fa81e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800fa829`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800fa834`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800fa5e1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800fa6b9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800fa6c8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800fa6d7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800fa6e6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800fa720`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800fa733`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800fa745`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800fa7b9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800fa7cf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800fa5e1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800fa6b9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800fa6c8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800fa6d7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800fa6e6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800fa720`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800fa733`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800fa745`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800fa7b9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800fa7cf`

## string_xrefs

- `0x1800fa783`: `onecoreuap\enduser\winstore\installservice\lib\uwainstallwork.cpp`
- `0x1800fa808`: `onecoreuap\enduser\winstore\installservice\lib\uwainstallwork.cpp`
- `0x1800fa776`: `UWAInstallWork::_RecordAcquisitionIdentity`
- `0x1800fa7fb`: `UWAInstallWork::_RecordAcquisitionIdentity`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall UWAInstallWork::_RecordAcquisitionIdentity(UWAInstallWork *this)
{
  HSTRING v2; // rcx
  int v3; // edi
  __int64 *v4; // r15
  __int64 *v5; // r12
  struct _GUID v6; // xmm6
  __int64 v7; // rdi
  int (__fastcall *v8)(__int64, HSTRING *); // rbx
  const unsigned __int16 *v9; // rsi
  const unsigned __int16 *v10; // rdi
  const unsigned __int16 *v11; // rbx
  Appx *v12; // rax
  int v13; // esi
  HSTRING v14; // rcx
  const unsigned __int16 *v15; // rax
  HSTRING v16; // rcx
  PCWSTR StringRawBuffer; // rbx
  const unsigned __int16 *v18; // rax
  unsigned __int16 *v19; // [rsp+28h] [rbp-48h]
  struct _GUID v20; // [rsp+50h] [rbp-20h] BYREF
  HSTRING v21; // [rsp+B0h] [rbp+40h] BYREF
  HSTRING string; // [rsp+B8h] [rbp+48h] BYREF
  HSTRING v23; // [rsp+C0h] [rbp+50h] BYREF
  HSTRING v24; // [rsp+C8h] [rbp+58h] BYREF

  v2 = (HSTRING)*((_QWORD *)this + 9);
  if ( v2 && WindowsGetStringRawBuffer(v2, 0) )
  {
    v20 = GUID_NULL;
    WindowsDeleteString(0);
    string = 0;
    WindowsDeleteString(0);
    v23 = 0;
    WindowsDeleteString(0);
    v24 = 0;
    v3 = ParseIdentityData(*((HSTRING *)this + 9), &v24, &v23, &string, &v20);
    if ( v3 < 0 )
    {
      v16 = (HSTRING)*((_QWORD *)this + 9);
      if ( v16 )
        StringRawBuffer = WindowsGetStringRawBuffer(v16, 0);
      else
        StringRawBuffer = 0;
      v18 = WindowsGetStringRawBuffer(*((HSTRING *)this + 59), 0);
      LogMessage(
        2u,
        "onecoreuap\\enduser\\winstore\\installservice\\lib\\uwainstallwork.cpp",
        0x1A90u,
        "UWAInstallWork::_RecordAcquisitionIdentity",
        v3,
        L"Invalid identity data: %s",
        (const char *)this + 304,
        v18,
        StringRawBuffer);
    }
    else
    {
      v4 = (__int64 *)*((_QWORD *)this + 146);
      v5 = (__int64 *)*((_QWORD *)this + 147);
      if ( v4 != v5 )
      {
        v6 = v20;
        do
        {
          v21 = 0;
          v7 = *v4;
          v8 = *(int (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)*v4 + 88LL);
          WindowsDeleteString(0);
          v21 = 0;
          if ( v8(v7, &v21) >= 0 )
          {
            if ( v21 )
            {
              v9 = WindowsGetStringRawBuffer(string, 0);
              v10 = WindowsGetStringRawBuffer(v23, 0);
              v11 = WindowsGetStringRawBuffer(v24, 0);
              v12 = (Appx *)WindowsGetStringRawBuffer(v21, 0);
              v20 = v6;
              v13 = Appx::SetPackageAcquisitionInfoForPackage(
                      v12,
                      v11,
                      v10,
                      v9,
                      (const unsigned __int16 *)&v20,
                      (struct _GUID *)v19);
              if ( v13 < 0 )
              {
                v14 = (HSTRING)*((_QWORD *)this + 9);
                if ( v14 )
                  WindowsGetStringRawBuffer(v14, 0);
                WindowsGetStringRawBuffer(v21, 0);
                v15 = WindowsGetStringRawBuffer(*((HSTRING *)this + 59), 0);
                LogMessage(
                  2u,
                  "onecoreuap\\enduser\\winstore\\installservice\\lib\\uwainstallwork.cpp",
                  0x1A89u,
                  "UWAInstallWork::_RecordAcquisitionIdentity",
                  v13,
                  L"SetPackageAcquisitionInfoForPackage failure ignored: PFN = %s, IdentityData = %s",
                  (const char *)this + 304,
                  v15);
              }
            }
          }
          WindowsDeleteString(v21);
          ++v4;
        }
        while ( v4 != v5 );
      }
    }
    WindowsDeleteString(string);
    WindowsDeleteString(v23);
    WindowsDeleteString(v24);
  }
}

```

## disassembly

```asm
0x1800fa5b8  push    rbp
0x1800fa5ba  push    rbx
0x1800fa5bb  push    rsi
0x1800fa5bc  push    rdi
0x1800fa5bd  push    r12
0x1800fa5bf  push    r14
0x1800fa5c1  push    r15
0x1800fa5c3  mov     rbp, rsp
0x1800fa5c6  sub     rsp, 70h
0x1800fa5ca  movaps  [rsp+70h+var_10], xmm6
0x1800fa5cf  mov     r14, rcx
0x1800fa5d2  mov     rcx, [rcx+48h]; string
0x1800fa5d6  test    rcx, rcx
0x1800fa5d9  jz      loc_1800FA83A
0x1800fa5df  xor     edx, edx; length
0x1800fa5e1  call    cs:__imp_WindowsGetStringRawBuffer
0x1800fa5e7  test    rax, rax
0x1800fa5ea  jz      loc_1800FA83A
0x1800fa5f0  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x1800fa5f7  movdqu  xmmword ptr [rbp+var_20.Data1], xmm0
0x1800fa5fc  xor     ecx, ecx; string
0x1800fa5fe  call    cs:__imp_WindowsDeleteString
0x1800fa604  mov     [rbp+string], 0
0x1800fa60c  xor     ecx, ecx; string
0x1800fa60e  call    cs:__imp_WindowsDeleteString
0x1800fa614  mov     [rbp+arg_10], 0
0x1800fa61c  xor     ecx, ecx; string
0x1800fa61e  call    cs:__imp_WindowsDeleteString
0x1800fa624  mov     [rbp+arg_18], 0
0x1800fa62c  lea     rax, [rbp+var_20]
0x1800fa630  mov     [rsp+70h+var_50], rax; struct _GUID *
0x1800fa635  lea     r9, [rbp+string]; HSTRING *
0x1800fa639  lea     r8, [rbp+arg_10]; HSTRING *
0x1800fa63d  lea     rdx, [rbp+arg_18]; HSTRING *
0x1800fa641  mov     rcx, [r14+48h]; HSTRING
0x1800fa645  call    ?ParseIdentityData@@YAJPEAUHSTRING__@@PEAPEAU1@11PEAU_GUID@@@Z; ParseIdentityData(HSTRING__ *,HSTRING__ * *,HSTRING__ * *,HSTRING__ * *,_GUID *)
0x1800fa64a  mov     edi, eax
0x1800fa64c  test    eax, eax
0x1800fa64e  js      loc_1800FA7AE
0x1800fa654  mov     r15, [r14+490h]
0x1800fa65b  mov     r12, [r14+498h]
0x1800fa662  cmp     r15, r12
0x1800fa665  jz      loc_1800FA81A
0x1800fa66b  movups  xmm6, xmmword ptr [rbp+var_20.Data1]
0x1800fa66f  mov     [rbp+arg_0], 0
0x1800fa677  mov     rdi, [r15]
0x1800fa67a  mov     rax, [rdi]
0x1800fa67d  mov     rbx, [rax+58h]
0x1800fa681  xor     ecx, ecx; string
0x1800fa683  call    cs:__imp_WindowsDeleteString
0x1800fa689  mov     [rbp+arg_0], 0
0x1800fa691  lea     rdx, [rbp+arg_0]
0x1800fa695  mov     rcx, rdi
0x1800fa698  mov     rax, rbx
0x1800fa69b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fa6a0  test    eax, eax
0x1800fa6a2  js      loc_1800FA795
0x1800fa6a8  cmp     [rbp+arg_0], 0
0x1800fa6ad  jz      loc_1800FA795
0x1800fa6b3  xor     edx, edx; length
0x1800fa6b5  mov     rcx, [rbp+string]; string
0x1800fa6b9  call    cs:__imp_WindowsGetStringRawBuffer
0x1800fa6bf  mov     rsi, rax
0x1800fa6c2  xor     edx, edx; length
0x1800fa6c4  mov     rcx, [rbp+arg_10]; string
0x1800fa6c8  call    cs:__imp_WindowsGetStringRawBuffer
0x1800fa6ce  mov     rdi, rax
0x1800fa6d1  xor     edx, edx; length
0x1800fa6d3  mov     rcx, [rbp+arg_18]; string
0x1800fa6d7  call    cs:__imp_WindowsGetStringRawBuffer
0x1800fa6dd  mov     rbx, rax
0x1800fa6e0  xor     edx, edx; length
0x1800fa6e2  mov     rcx, [rbp+arg_0]; string
0x1800fa6e6  call    cs:__imp_WindowsGetStringRawBuffer
0x1800fa6ec  movdqu  xmmword ptr [rbp+var_20.Data1], xmm6
0x1800fa6f1  lea     rcx, [rbp+var_20]
0x1800fa6f5  mov     [rsp+70h+var_50], rcx; Buf1
0x1800fa6fa  mov     r9, rsi; unsigned __int16 *
0x1800fa6fd  mov     r8, rdi; unsigned __int16 *
0x1800fa700  mov     rdx, rbx; unsigned __int16 *
0x1800fa703  mov     rcx, rax; this
0x1800fa706  call    ?SetPackageAcquisitionInfoForPackage@Appx@@YAJPEBG000U_GUID@@@Z; Appx::SetPackageAcquisitionInfoForPackage(ushort const *,ushort const *,ushort const *,ushort const *,_GUID)
0x1800fa70b  mov     esi, eax
0x1800fa70d  test    eax, eax
0x1800fa70f  jns     loc_1800FA795
0x1800fa715  mov     rcx, [r14+48h]; string
0x1800fa719  test    rcx, rcx
0x1800fa71c  jz      short loc_1800FA72B
0x1800fa71e  xor     edx, edx; length
0x1800fa720  call    cs:__imp_WindowsGetStringRawBuffer
0x1800fa726  mov     rdi, rax
0x1800fa729  jmp     short loc_1800FA72D
0x1800fa72b  xor     edi, edi
0x1800fa72d  xor     edx, edx; length
0x1800fa72f  mov     rcx, [rbp+arg_0]; string
0x1800fa733  call    cs:__imp_WindowsGetStringRawBuffer
0x1800fa739  mov     rbx, rax
0x1800fa73c  xor     edx, edx; length
0x1800fa73e  mov     rcx, [r14+1D8h]; string
0x1800fa745  call    cs:__imp_WindowsGetStringRawBuffer
0x1800fa74b  lea     rcx, [r14+130h]
0x1800fa752  mov     [rsp+70h+var_28], rdi
0x1800fa757  mov     [rsp+70h+var_30], rbx
0x1800fa75c  mov     [rsp+70h+var_38], rax; unsigned __int16 *
0x1800fa761  mov     [rsp+70h+var_40], rcx; char *
0x1800fa766  lea     rax, aSetpackageacqu; "SetPackageAcquisitionInfoForPackage fai"...
0x1800fa76d  mov     [rsp+70h+var_48], rax; unsigned __int16 *
0x1800fa772  mov     dword ptr [rsp+70h+var_50], esi; int
0x1800fa776  lea     r9, aUwainstallwork_46; "UWAInstallWork::_RecordAcquisitionIdent"...
0x1800fa77d  mov     r8d, 1A89h; unsigned int
0x1800fa783  lea     rdx, aOnecoreuapEndu_12; "onecoreuap\\enduser\\winstore\\installs"...
0x1800fa78a  mov     ecx, 2; unsigned int
0x1800fa78f  call    ?LogMessage@@YAXIPEBDI0JPEBG01ZZ; LogMessage(uint,char const *,uint,char const *,long,ushort const *,char const *,ushort const *,...)
0x1800fa794  nop
0x1800fa795  mov     rcx, [rbp+arg_0]; string
0x1800fa799  call    cs:__imp_WindowsDeleteString
0x1800fa79f  add     r15, 8
0x1800fa7a3  cmp     r15, r12
0x1800fa7a6  jnz     loc_1800FA66F
0x1800fa7ac  jmp     short loc_1800FA81A
0x1800fa7ae  mov     rcx, [r14+48h]; string
0x1800fa7b2  test    rcx, rcx
0x1800fa7b5  jz      short loc_1800FA7C4
0x1800fa7b7  xor     edx, edx; length
0x1800fa7b9  call    cs:__imp_WindowsGetStringRawBuffer
0x1800fa7bf  mov     rbx, rax
0x1800fa7c2  jmp     short loc_1800FA7C6
0x1800fa7c4  xor     ebx, ebx
0x1800fa7c6  xor     edx, edx; length
0x1800fa7c8  mov     rcx, [r14+1D8h]; string
0x1800fa7cf  call    cs:__imp_WindowsGetStringRawBuffer
0x1800fa7d5  lea     rcx, [r14+130h]
0x1800fa7dc  mov     [rsp+70h+var_30], rbx
0x1800fa7e1  mov     [rsp+70h+var_38], rax; unsigned __int16 *
0x1800fa7e6  mov     [rsp+70h+var_40], rcx; char *
0x1800fa7eb  lea     rax, aInvalidIdentit; "Invalid identity data: %s"
0x1800fa7f2  mov     [rsp+70h+var_48], rax; unsigned __int16 *
0x1800fa7f7  mov     dword ptr [rsp+70h+var_50], edi; int
0x1800fa7fb  lea     r9, aUwainstallwork_46; "UWAInstallWork::_RecordAcquisitionIdent"...
0x1800fa802  mov     r8d, 1A90h; unsigned int
0x1800fa808  lea     rdx, aOnecoreuapEndu_12; "onecoreuap\\enduser\\winstore\\installs"...
0x1800fa80f  mov     ecx, 2; unsigned int
0x1800fa814  call    ?LogMessage@@YAXIPEBDI0JPEBG01ZZ; LogMessage(uint,char const *,uint,char const *,long,ushort const *,char const *,ushort const *,...)
0x1800fa819  nop
0x1800fa81a  mov     rcx, [rbp+string]; string
0x1800fa81e  call    cs:__imp_WindowsDeleteString
0x1800fa824  nop
0x1800fa825  mov     rcx, [rbp+arg_10]; string
0x1800fa829  call    cs:__imp_WindowsDeleteString
0x1800fa82f  nop
0x1800fa830  mov     rcx, [rbp+arg_18]; string
0x1800fa834  call    cs:__imp_WindowsDeleteString
0x1800fa83a  movaps  xmm6, [rsp+70h+var_10]
0x1800fa83f  add     rsp, 70h
0x1800fa843  pop     r15
0x1800fa845  pop     r14
0x1800fa847  pop     r12
0x1800fa849  pop     rdi
0x1800fa84a  pop     rsi
0x1800fa84b  pop     rbx
0x1800fa84c  pop     rbp
0x1800fa84d  retn
```
