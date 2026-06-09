# tip2::details::shared_data<0,0,0>::start(void)

- ea: `0x1800280f4`
- end: `0x18002830e`
- name: `?start@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAA?AU_GUID@@XZ`
- size: `538`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180019810`

## callees

- `0x180002240`
- `0x180027e30`
- `0x1800280f4`
- `0x180058010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800281fd`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180028285`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800281fd`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180028285`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800281e6`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18002826e`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800281e6`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18002826e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180028134`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180028134`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800282db`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800282db`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028246`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028246`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800282a2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800282a2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800282cd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800282cd`

## string_xrefs

- `0x1800281df`: `kernelbase.dll`
- `0x180028267`: `kernelbase.dll`
- `0x1800281f3`: `TestCreate`

## pseudocode

```c
_OWORD *__fastcall tip2::details::shared_data<0,0,0>::start(__int64 a1, _OWORD *a2)
{
  struct _RTL_CRITICAL_SECTION *v4; // rsi
  __int64 v5; // r8
  bool v6; // al
  _OWORD *v7; // r14
  __int64 v8; // r15
  unsigned int v9; // edi
  char v10; // r12
  FARPROC ProcAddress; // rax
  HMODULE ModuleHandleW; // rax
  __int64 v13; // r12
  __int64 v14; // rdi
  DWORD LastError; // r15d
  FARPROC v16; // rax
  HMODULE v17; // rax
  unsigned int v19; // [rsp+40h] [rbp-C0h]
  LPVOID pv; // [rsp+50h] [rbp-B0h] BYREF
  char v21; // [rsp+58h] [rbp-A8h]
  int v22; // [rsp+59h] [rbp-A7h] BYREF
  char v23; // [rsp+5Dh] [rbp-A3h]
  char v24; // [rsp+5Eh] [rbp-A2h] BYREF
  char v25; // [rsp+859h] [rbp+759h] BYREF
  int *v26; // [rsp+860h] [rbp+760h]
  char *v27; // [rsp+868h] [rbp+768h]
  char *v28; // [rsp+870h] [rbp+770h]

  v4 = (struct _RTL_CRITICAL_SECTION *)(a1 + 192);
  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 192));
  pv = 0;
  v21 = 0;
  v26 = &v22;
  v28 = &v25;
  v22 = -2143256512;
  v23 = 0;
  v27 = &v24;
  v6 = (*(_DWORD *)(a1 + 64) & 0x800) != 0 && (*(_DWORD *)(a1 + 20) & 0x8000) == 0;
  v7 = (_OWORD *)(a1 + 144);
  if ( v6 )
    v8 = tip2::details::shared_data<0,0,0>::serialize_data(a1, &pv, 1);
  else
    v8 = 0;
  v9 = *(_DWORD *)(a1 + 20);
  v10 = *(_BYTE *)(a1 + 32);
  v19 = *(_DWORD *)(a1 + 16);
  ProcAddress = (FARPROC)`TestCreate'::`2'::s_pfnTestCreate;
  if ( `TestCreate'::`2'::s_pfnTestCreate )
    goto LABEL_13;
  ModuleHandleW = g_tip_details_kernelbaseModuleHandle;
  if ( !g_tip_details_kernelbaseModuleHandle )
  {
    ModuleHandleW = GetModuleHandleW(L"kernelbase.dll");
    g_tip_details_kernelbaseModuleHandle = ModuleHandleW;
  }
  ProcAddress = GetProcAddress(ModuleHandleW, "TestCreate");
  `TestCreate'::`2'::s_pfnTestCreate = (__int64)ProcAddress;
  if ( ProcAddress )
  {
LABEL_13:
    LOBYTE(v5) = v10;
    v13 = ((__int64 (__fastcall *)(_QWORD, _QWORD, __int64, _QWORD, __int64, __int64))ProcAddress)(
            v19,
            0,
            v5,
            v9,
            v8,
            a1 + 144);
  }
  else
  {
    *v7 = 0;
    v13 = 0;
  }
  v14 = *(_QWORD *)(a1 + 240);
  if ( v14 )
  {
    LastError = GetLastError();
    v16 = (FARPROC)`TestClose'::`2'::s_pfnTestClose;
    if ( `TestClose'::`2'::s_pfnTestClose )
      goto LABEL_19;
    v17 = g_tip_details_kernelbaseModuleHandle;
    if ( !g_tip_details_kernelbaseModuleHandle )
    {
      v17 = GetModuleHandleW(L"kernelbase.dll");
      g_tip_details_kernelbaseModuleHandle = v17;
    }
    v16 = GetProcAddress(v17, "TestClose");
    `TestClose'::`2'::s_pfnTestClose = (__int64)v16;
    if ( v16 )
LABEL_19:
      ((void (__fastcall *)(__int64))v16)(v14);
    SetLastError(LastError);
  }
  *(_QWORD *)(a1 + 240) = v13;
  *(_DWORD *)(a1 + 184) = 1;
  *a2 = *v7;
  if ( pv )
    CoTaskMemFree(pv);
  if ( v4 )
    LeaveCriticalSection(v4);
  return a2;
}

```

## disassembly

```asm
0x1800280f4  mov     [rsp-8+arg_10], rbx
0x1800280f9  push    rbp
0x1800280fa  push    rsi
0x1800280fb  push    rdi
0x1800280fc  push    r12
0x1800280fe  push    r13
0x180028100  push    r14
0x180028102  push    r15
0x180028104  lea     rbp, [rsp-790h]
0x18002810c  sub     rsp, 890h
0x180028113  mov     rax, cs:__security_cookie
0x18002811a  xor     rax, rsp
0x18002811d  mov     [rbp+7C0h+var_40], rax
0x180028124  mov     r13, rdx
0x180028127  mov     rbx, rcx
0x18002812a  lea     rsi, [rcx+0C0h]
0x180028131  mov     rcx, rsi; lpCriticalSection
0x180028134  call    cs:__imp_EnterCriticalSection
0x18002813a  mov     [rsp+8C0h+pv], 0
0x180028143  mov     [rsp+8C0h+var_868], 0
0x180028148  lea     rax, [rsp+8C0h+var_867]
0x18002814d  mov     [rbp+7C0h+var_60], rax
0x180028154  lea     rax, [rbp+7C0h+var_67]
0x18002815b  mov     [rbp+7C0h+var_50], rax
0x180028162  mov     [rsp+8C0h+var_867], 80408040h
0x18002816a  mov     [rsp+8C0h+var_863], 0
0x18002816f  lea     rax, [rsp+8C0h+var_862]
0x180028174  mov     [rbp+7C0h+var_58], rax
0x18002817b  test    dword ptr [rbx+40h], 800h
0x180028182  jz      short loc_180028191
0x180028184  test    dword ptr [rbx+14h], 8000h
0x18002818b  jnz     short loc_180028191
0x18002818d  mov     al, 1
0x18002818f  jmp     short loc_180028193
0x180028191  xor     al, al
0x180028193  lea     r14, [rbx+90h]
0x18002819a  test    al, al
0x18002819c  jz      short loc_1800281B6
0x18002819e  mov     r8d, 1
0x1800281a4  lea     rdx, [rsp+8C0h+pv]
0x1800281a9  mov     rcx, rbx
0x1800281ac  call    ?serialize_data@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAPEBDAEAVwrite_buffer@tson@@W4serialize_options@23@@Z; tip2::details::shared_data<0,0,0>::serialize_data(tson::write_buffer &,tip2::details::serialize_options)
0x1800281b1  mov     r15, rax
0x1800281b4  jmp     short loc_1800281B9
0x1800281b6  xor     r15d, r15d
0x1800281b9  mov     edi, [rbx+14h]
0x1800281bc  mov     r12b, [rbx+20h]
0x1800281c0  mov     eax, [rbx+10h]
0x1800281c3  mov     [rsp+8C0h+var_880], eax
0x1800281c7  mov     rax, cs:?s_pfnTestCreate@?1??TestCreate@@9@4P6APEAUHTIPTEST__@@IW4TestRetrievalOptions@@W4TestStorage@@W4TestProperties@@PEBDPEAU_GUID@@@ZEA; HTIPTEST__ * (*`TestCreate'::`2'::s_pfnTestCreate)(uint,TestRetrievalOptions,TestStorage,TestProperties,char const *,_GUID *)
0x1800281ce  test    rax, rax
0x1800281d1  jnz     short loc_18002821C
0x1800281d3  mov     rax, cs:g_tip_details_kernelbaseModuleHandle
0x1800281da  test    rax, rax
0x1800281dd  jnz     short loc_1800281F3
0x1800281df  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x1800281e6  call    cs:__imp_GetModuleHandleW
0x1800281ec  mov     cs:g_tip_details_kernelbaseModuleHandle, rax
0x1800281f3  lea     rdx, aTestcreate; "TestCreate"
0x1800281fa  mov     rcx, rax; hModule
0x1800281fd  call    cs:__imp_GetProcAddress
0x180028203  mov     cs:?s_pfnTestCreate@?1??TestCreate@@9@4P6APEAUHTIPTEST__@@IW4TestRetrievalOptions@@W4TestStorage@@W4TestProperties@@PEBDPEAU_GUID@@@ZEA, rax; HTIPTEST__ * (*`TestCreate'::`2'::s_pfnTestCreate)(uint,TestRetrievalOptions,TestStorage,TestProperties,char const *,_GUID *)
0x18002820a  test    rax, rax
0x18002820d  jnz     short loc_18002821C
0x18002820f  xorps   xmm0, xmm0
0x180028212  movdqu  xmmword ptr [r14], xmm0
0x180028217  xor     r12d, r12d
0x18002821a  jmp     short loc_18002823A
0x18002821c  mov     [rsp+8C0h+var_898], r14
0x180028221  mov     [rsp+8C0h+var_8A0], r15
0x180028226  mov     r9d, edi
0x180028229  mov     r8b, r12b
0x18002822c  xor     edx, edx
0x18002822e  mov     ecx, [rsp+8C0h+var_880]
0x180028232  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028237  mov     r12, rax
0x18002823a  mov     rdi, [rbx+0F0h]
0x180028241  test    rdi, rdi
0x180028244  jz      short loc_1800282A8
0x180028246  call    cs:__imp_GetLastError
0x18002824c  mov     r15d, eax
0x18002824f  mov     rax, cs:?s_pfnTestClose@?1??TestClose@@9@4P6AXPEAUHTIPTEST__@@@ZEA; void (*`TestClose'::`2'::s_pfnTestClose)(HTIPTEST__ *)
0x180028256  test    rax, rax
0x180028259  jnz     short loc_180028297
0x18002825b  mov     rax, cs:g_tip_details_kernelbaseModuleHandle
0x180028262  test    rax, rax
0x180028265  jnz     short loc_18002827B
0x180028267  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x18002826e  call    cs:__imp_GetModuleHandleW
0x180028274  mov     cs:g_tip_details_kernelbaseModuleHandle, rax
0x18002827b  lea     rdx, aTestclose; "TestClose"
0x180028282  mov     rcx, rax; hModule
0x180028285  call    cs:__imp_GetProcAddress
0x18002828b  mov     cs:?s_pfnTestClose@?1??TestClose@@9@4P6AXPEAUHTIPTEST__@@@ZEA, rax; void (*`TestClose'::`2'::s_pfnTestClose)(HTIPTEST__ *)
0x180028292  test    rax, rax
0x180028295  jz      short loc_18002829F
0x180028297  mov     rcx, rdi
0x18002829a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002829f  mov     ecx, r15d; dwErrCode
0x1800282a2  call    cs:__imp_SetLastError
0x1800282a8  mov     [rbx+0F0h], r12
0x1800282af  mov     dword ptr [rbx+0B8h], 1
0x1800282b9  movups  xmm0, xmmword ptr [r14]
0x1800282bd  movdqu  xmmword ptr [r13+0], xmm0
0x1800282c3  mov     rcx, [rsp+8C0h+pv]; pv
0x1800282c8  test    rcx, rcx
0x1800282cb  jz      short loc_1800282D3
0x1800282cd  call    cs:__imp_CoTaskMemFree
0x1800282d3  test    rsi, rsi
0x1800282d6  jz      short loc_1800282E1
0x1800282d8  mov     rcx, rsi; lpCriticalSection
0x1800282db  call    cs:__imp_LeaveCriticalSection
0x1800282e1  mov     rax, r13
0x1800282e4  mov     rcx, [rbp+7C0h+var_40]
0x1800282eb  xor     rcx, rsp; StackCookie
0x1800282ee  call    __security_check_cookie
0x1800282f3  mov     rbx, [rsp+8C0h+arg_10]
0x1800282fb  add     rsp, 890h
0x180028302  pop     r15
0x180028304  pop     r14
0x180028306  pop     r13
0x180028308  pop     r12
0x18002830a  pop     rdi
0x18002830b  pop     rsi
0x18002830c  pop     rbp
0x18002830d  retn
```
