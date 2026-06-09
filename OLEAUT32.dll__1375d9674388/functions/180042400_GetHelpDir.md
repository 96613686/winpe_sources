# GetHelpDir

- ea: `0x180042400`
- end: `0x1800426a1`
- name: `GetHelpDir`
- size: `673`
- prototype: ``
- caller_count: `2`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18002fe70`
- `0x180051cd0`

## callees

- `0x180014f04`
- `0x180015104`
- `0x1800153bc`
- `0x180042400`
- `0x1800426a8`
- `0x18004d900`
- `0x18004e530`
- `0x18009c010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x18004254e`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x18004266d`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x18004254e`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x18004266d`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800425ea`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800425ea`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180042580`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180042580`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800424c7`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800424c7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800424e6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004261b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800424e6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004261b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18004253a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18004253a`

## pseudocode

```c
__int64 __fastcall GetHelpDir(__int64 *a1, __int64 a2, WCHAR *a3, int a4)
{
  unsigned __int64 v4; // r14
  __int64 v9; // rax
  unsigned int v10; // edi
  unsigned int v11; // r12d
  unsigned int v12; // r13d
  LPVOID v13; // rdi
  int (__fastcall *v14)(LPVOID, GUID *, _QWORD, _QWORD, UINT32, HSTRING *); // rbx
  PCWSTR StringRawBuffer; // rax
  unsigned int v16; // eax
  LPVOID v17; // rcx
  __int64 v18; // rax
  UINT32 length; // [rsp+40h] [rbp-99h] BYREF
  HSTRING string; // [rsp+48h] [rbp-91h] BYREF
  LPVOID ppv; // [rsp+50h] [rbp-89h] BYREF
  __int64 v22; // [rsp+58h] [rbp-81h] BYREF
  __int128 v23; // [rsp+60h] [rbp-79h] BYREF
  HKEY hkey; // [rsp+70h] [rbp-69h]
  GUID rguid; // [rsp+78h] [rbp-61h] BYREF
  OLECHAR sz[40]; // [rsp+90h] [rbp-49h] BYREF

  v4 = a4;
  if ( a4 < 2 )
    return 2147942487LL;
  v9 = *a1;
  v22 = 0;
  v10 = (*(__int64 (__fastcall **)(__int64 *, __int64 *))(v9 + 56))(a1, &v22);
  if ( v10 )
    goto LABEL_16;
  rguid = *(GUID *)v22;
  v11 = *(unsigned __int16 *)(v22 + 24);
  v12 = *(unsigned __int16 *)(v22 + 26);
  length = *(_DWORD *)(v22 + 16);
  (*(void (__fastcall **)(__int64 *))(*a1 + 96))(a1);
  ppv = 0;
  string = 0;
  Microsoft::WRL::ComPtr<ITypeInfo>::InternalRelease(&ppv);
  if ( CoCreateInstance(
         &GUID_00000346_0000_0000_c000_000000000046,
         0,
         1u,
         &GUID_e085ad58_b839_4625_b40b_4cc546e82d75,
         &ppv) < 0
    || (v13 = ppv,
        v14 = *(int (__fastcall **)(LPVOID, GUID *, _QWORD, _QWORD, UINT32, HSTRING *))(*(_QWORD *)ppv + 32LL),
        WindowsDeleteString(string),
        string = 0,
        v14(v13, &rguid, v11, v12, length, &string) < 0) )
  {
    memset_0(sz, 0, 0x4Eu);
    StringFromGUID2(&rguid, sz, 39);
    hkey = 0;
    v23 = 0;
    v10 = OpenTypeLibKey(sz, (unsigned __int16)v11, v12, 0, (HKEY *)&v23, 0, 0);
    if ( !v10 )
    {
      length = v4;
      if ( RegGetValueW(hkey, L"HELPDIR", 0, 6u, 0, a3, &length) )
      {
        v10 = -2147319780;
      }
      else if ( !(unsigned int)FFileExists(a3) )
      {
        v10 = -2147287038;
      }
    }
    TLIBKEY::~TLIBKEY((TLIBKEY *)&v23);
  }
  else
  {
    length = 0;
    StringRawBuffer = WindowsGetStringRawBuffer(string, &length);
    v16 = _o_wcsncpy_s(a3, v4 >> 1, StringRawBuffer);
    a3[(v4 >> 1) - 1] = 0;
    v10 = v16;
  }
  WindowsDeleteString(string);
  v17 = ppv;
  string = 0;
  if ( ppv )
  {
    ppv = 0;
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v17 + 16LL))(v17);
  }
  if ( v10 )
  {
LABEL_16:
    v18 = -1;
    do
      ++v18;
    while ( *(_WORD *)(a2 + 2 * v18) );
    if ( (_DWORD)v18 )
    {
      _o_wcsncpy_s(a3, v4 >> 1, a2);
      a3[(v4 >> 1) - 1] = 0;
    }
    else
    {
      *a3 = 0;
    }
  }
  return v10;
}

```

## disassembly

```asm
0x180042400  push    rbp
0x180042402  push    rbx
0x180042403  push    rsi
0x180042404  push    rdi
0x180042405  push    r12
0x180042407  push    r13
0x180042409  push    r14
0x18004240b  push    r15
0x18004240d  lea     rbp, [rsp-1Fh]
0x180042412  sub     rsp, 0F8h
0x180042419  mov     rax, cs:__security_cookie
0x180042420  xor     rax, rsp
0x180042423  mov     [rbp+57h+var_50], rax
0x180042427  movsxd  r14, r9d
0x18004242a  mov     rsi, r8
0x18004242d  mov     r15, rdx
0x180042430  mov     rbx, rcx
0x180042433  cmp     r14d, 2
0x180042437  jge     short loc_180042443
0x180042439  mov     eax, 80070057h
0x18004243e  jmp     loc_180042681
0x180042443  mov     rax, [rcx]
0x180042446  lea     rdx, [rsp+130h+var_D8]
0x18004244b  xor     r12d, r12d
0x18004244e  mov     [rsp+130h+var_D8], r12
0x180042453  mov     rax, [rax+38h]
0x180042457  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004245c  mov     edi, eax
0x18004245e  test    eax, eax
0x180042460  jnz     loc_180042647
0x180042466  mov     rdx, [rsp+130h+var_D8]
0x18004246b  mov     rcx, rbx
0x18004246e  movups  xmm0, xmmword ptr [rdx]
0x180042471  movdqu  xmmword ptr [rbp+57h+rguid.Data1], xmm0
0x180042476  mov     eax, [rdx+10h]
0x180042479  movzx   r12d, word ptr [rdx+18h]
0x18004247e  movzx   r13d, word ptr [rdx+1Ah]
0x180042483  mov     [rsp+130h+length], eax
0x180042487  mov     rax, [rbx]
0x18004248a  mov     rax, [rax+60h]
0x18004248e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042493  xor     ebx, ebx
0x180042495  lea     rcx, [rsp+130h+var_E0]
0x18004249a  mov     [rsp+130h+var_E0], rbx
0x18004249f  mov     [rsp+130h+string], rbx
0x1800424a4  call    ?InternalRelease@?$ComPtr@UITypeInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ITypeInfo>::InternalRelease(void)
0x1800424a9  lea     rax, [rsp+130h+var_E0]
0x1800424ae  xor     edx, edx; pUnkOuter
0x1800424b0  lea     r9, _GUID_e085ad58_b839_4625_b40b_4cc546e82d75; riid
0x1800424b7  mov     [rsp+130h+ppv], rax; ppv
0x1800424bc  lea     r8d, [rdi+1]; dwClsContext
0x1800424c0  lea     rcx, _GUID_00000346_0000_0000_c000_000000000046; rclsid
0x1800424c7  call    cs:__imp_CoCreateInstance
0x1800424cd  test    eax, eax
0x1800424cf  js      loc_180042563
0x1800424d5  mov     rdi, [rsp+130h+var_E0]
0x1800424da  mov     rcx, [rsp+130h+string]; string
0x1800424df  mov     rax, [rdi]
0x1800424e2  mov     rbx, [rax+20h]
0x1800424e6  call    cs:__imp_WindowsDeleteString
0x1800424ec  lea     rax, [rsp+130h+string]
0x1800424f1  mov     [rsp+130h+string], 0
0x1800424fa  mov     [rsp+130h+pvData], rax
0x1800424ff  lea     rdx, [rbp+57h+rguid]
0x180042503  mov     eax, [rsp+130h+length]
0x180042507  mov     r9d, r13d
0x18004250a  mov     dword ptr [rsp+130h+ppv], eax
0x18004250e  mov     r8d, r12d
0x180042511  mov     rax, rbx
0x180042514  mov     rcx, rdi
0x180042517  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004251c  xor     ebx, ebx
0x18004251e  test    eax, eax
0x180042520  js      short loc_180042563
0x180042522  mov     rcx, [rsp+130h+string]; string
0x180042527  lea     rdx, [rsp+130h+length]; length
0x18004252c  mov     rbx, r14
0x18004252f  xor     r12d, r12d
0x180042532  shr     rbx, 1
0x180042535  mov     [rsp+130h+length], r12d
0x18004253a  call    cs:__imp_WindowsGetStringRawBuffer
0x180042540  mov     r9d, [rsp+130h+length]
0x180042545  mov     rdx, rbx
0x180042548  mov     r8, rax
0x18004254b  mov     rcx, rsi
0x18004254e  call    cs:__imp__o_wcsncpy_s
0x180042554  mov     [rsi+rbx*2-2], r12w
0x18004255a  mov     edi, eax
0x18004255c  xor     ebx, ebx
0x18004255e  jmp     loc_180042616
0x180042563  xor     edx, edx; Val
0x180042565  lea     rcx, [rbp+57h+sz]; void *
0x180042569  lea     r8d, [rdx+4Eh]; Size
0x18004256d  call    memset_0
0x180042572  mov     r8d, 27h ; '''; cchMax
0x180042578  lea     rdx, [rbp+57h+sz]; lpsz
0x18004257c  lea     rcx, [rbp+57h+rguid]; rguid
0x180042580  call    cs:__imp_StringFromGUID2
0x180042586  xorps   xmm0, xmm0
0x180042589  mov     [rsp+130h+pcbData], rbx; unsigned __int16 *
0x18004258e  lea     rax, [rbp+57h+var_D0]
0x180042592  mov     [rsp+130h+pvData], rbx; unsigned __int16 *
0x180042597  xor     r9d, r9d; int
0x18004259a  mov     [rsp+130h+ppv], rax; struct TLIBKEY *
0x18004259f  movzx   r8d, r13w; unsigned __int16
0x1800425a3  mov     [rbp+57h+hkey], rbx
0x1800425a7  movzx   edx, r12w; unsigned __int16
0x1800425ab  lea     rcx, [rbp+57h+sz]; lpSubKey
0x1800425af  movdqu  [rbp+57h+var_D0], xmm0
0x1800425b4  call    ?OpenTypeLibKey@@YAJPEBGGGHPEAUTLIBKEY@@PEAG2@Z; OpenTypeLibKey(ushort const *,ushort,ushort,int,TLIBKEY *,ushort *,ushort *)
0x1800425b9  mov     edi, eax
0x1800425bb  test    eax, eax
0x1800425bd  jnz     short loc_18004260D
0x1800425bf  mov     rcx, [rbp+57h+hkey]; hkey
0x1800425c3  lea     rax, [rsp+130h+length]
0x1800425c8  mov     [rsp+130h+pcbData], rax; pcbData
0x1800425cd  lea     r9d, [rdi+6]; dwFlags
0x1800425d1  mov     [rsp+130h+pvData], rsi; pvData
0x1800425d6  lea     rdx, ?HELPDIR@Constants@Catalog@Com@@3QBGB; "HELPDIR"
0x1800425dd  xor     r8d, r8d; lpValue
0x1800425e0  mov     [rsp+130h+ppv], rbx; pdwType
0x1800425e5  mov     [rsp+130h+length], r14d
0x1800425ea  call    cs:__imp_RegGetValueW
0x1800425f0  test    eax, eax
0x1800425f2  jz      short loc_1800425FB
0x1800425f4  mov     edi, 8002801Ch
0x1800425f9  jmp     short loc_18004260D
0x1800425fb  mov     rcx, rsi; lpWideCharStr
0x1800425fe  call    ?FFileExists@@YAHPEBG@Z; FFileExists(ushort const *)
0x180042603  test    eax, eax
0x180042605  mov     ecx, 80030002h
0x18004260a  cmovz   edi, ecx
0x18004260d  lea     rcx, [rbp+57h+var_D0]; this
0x180042611  call    ??1TLIBKEY@@QEAA@XZ; TLIBKEY::~TLIBKEY(void)
0x180042616  mov     rcx, [rsp+130h+string]; string
0x18004261b  call    cs:__imp_WindowsDeleteString
0x180042621  mov     rcx, [rsp+130h+var_E0]
0x180042626  mov     [rsp+130h+string], rbx
0x18004262b  test    rcx, rcx
0x18004262e  jz      short loc_180042641
0x180042630  mov     [rsp+130h+var_E0], rbx
0x180042635  mov     rax, [rcx]
0x180042638  mov     rax, [rax+10h]
0x18004263c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042641  test    edi, edi
0x180042643  jnz     short loc_180042649
0x180042645  jmp     short loc_18004267F
0x180042647  xor     ebx, ebx
0x180042649  or      rax, 0FFFFFFFFFFFFFFFFh
0x18004264d  inc     rax
0x180042650  cmp     [r15+rax*2], bx
0x180042655  jnz     short loc_18004264D
0x180042657  test    eax, eax
0x180042659  jz      short loc_18004267C
0x18004265b  mov     rbx, r14
0x18004265e  movsxd  r9, eax
0x180042661  shr     rbx, 1
0x180042664  mov     r8, r15
0x180042667  mov     rdx, rbx
0x18004266a  mov     rcx, rsi
0x18004266d  call    cs:__imp__o_wcsncpy_s
0x180042673  xor     eax, eax
0x180042675  mov     [rsi+rbx*2-2], ax
0x18004267a  jmp     short loc_18004267F
0x18004267c  mov     [rsi], bx
0x18004267f  mov     eax, edi
0x180042681  mov     rcx, [rbp+57h+var_50]
0x180042685  xor     rcx, rsp; StackCookie
0x180042688  call    __security_check_cookie
0x18004268d  add     rsp, 0F8h
0x180042694  pop     r15
0x180042696  pop     r14
0x180042698  pop     r13
0x18004269a  pop     r12
0x18004269c  pop     rdi
0x18004269d  pop     rsi
0x18004269e  pop     rbx
0x18004269f  pop     rbp
0x1800426a0  retn
```
