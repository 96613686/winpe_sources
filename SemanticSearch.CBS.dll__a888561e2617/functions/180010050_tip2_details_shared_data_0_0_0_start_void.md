# tip2::details::shared_data<0,0,0>::start(void)

- ea: `0x180010050`
- end: `0x18001022b`
- name: `?start@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAA?AU_GUID@@XZ`
- size: `475`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `8`
- callee_count: `6`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x18000a710`
- `0x18000cf50`
- `0x18001bcf0`
- `0x1800353b0`
- `0x180052c90`
- `0x180053610`
- `0x1800583b0`
- `0x18005bc90`

## callees

- `0x180010050`
- `0x180010a20`
- `0x180013e40`
- `0x18004c070`
- `0x18005e260`
- `0x18005e2c0`

## import_xrefs

- `KERNEL32!SetLastError` at `0x1800101bd`
- `KERNEL32!SetLastError` at `0x1800101bd`
- `KERNEL32!GetLastError` at `0x1800101ab`
- `KERNEL32!GetLastError` at `0x1800101ab`
- `KERNEL32!GetProcAddress` at `0x180010165`
- `KERNEL32!GetProcAddress` at `0x180010165`
- `KERNEL32!GetModuleHandleW` at `0x18001014e`
- `KERNEL32!GetModuleHandleW` at `0x18001014e`
- `KERNEL32!LeaveCriticalSection` at `0x1800101f7`
- `KERNEL32!LeaveCriticalSection` at `0x1800101f7`
- `KERNEL32!EnterCriticalSection` at `0x180010089`
- `KERNEL32!EnterCriticalSection` at `0x180010089`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800101e9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800101e9`

## string_xrefs

- `0x18001015b`: `TestCreate`
- `0x180010147`: `kernelbase.dll`

## pseudocode

```c
_OWORD *__fastcall tip2::details::shared_data<0,0,0>::start(__int64 a1, _OWORD *a2)
{
  struct _RTL_CRITICAL_SECTION *v4; // r14
  __int64 v5; // r15
  _OWORD *v6; // rsi
  __int64 v7; // r12
  unsigned int v8; // ebx
  unsigned __int8 v9; // r13
  FARPROC ProcAddress; // rax
  HMODULE ModuleHandleW; // rax
  __int64 v12; // rsi
  DWORD LastError; // ebx
  unsigned int v15; // [rsp+40h] [rbp-888h]
  LPVOID pv; // [rsp+50h] [rbp-878h] BYREF
  char v17; // [rsp+58h] [rbp-870h]
  int v18; // [rsp+59h] [rbp-86Fh] BYREF
  char v19; // [rsp+5Dh] [rbp-86Bh]
  _BYTE v20[2050]; // [rsp+5Eh] [rbp-86Ah] BYREF
  int *v21; // [rsp+860h] [rbp-68h]
  _BYTE *v22; // [rsp+868h] [rbp-60h]
  _BYTE *v23; // [rsp+870h] [rbp-58h]

  v4 = (struct _RTL_CRITICAL_SECTION *)(a1 + 192);
  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 192));
  memset(v20, 0, sizeof(v20));
  v5 = 0;
  pv = 0;
  v17 = 0;
  v21 = &v18;
  v23 = &v20[2043];
  v18 = -2143256512;
  v19 = 0;
  v22 = v20;
  if ( (*(_DWORD *)(a1 + 64) & 0x800) == 0 || (*(_DWORD *)(a1 + 20) & 0x8000) != 0 )
  {
    v6 = (_OWORD *)(a1 + 144);
    v7 = 0;
  }
  else
  {
    v6 = (_OWORD *)(a1 + 144);
    v7 = tip2::details::shared_data<0,0,0>::serialize_data(a1, &pv, 1);
  }
  v8 = *(_DWORD *)(a1 + 20);
  v9 = *(_BYTE *)(a1 + 32);
  v15 = *(_DWORD *)(a1 + 16);
  ProcAddress = (FARPROC)`TestCreate'::`2'::s_pfnTestCreate;
  if ( `TestCreate'::`2'::s_pfnTestCreate )
    goto LABEL_10;
  ModuleHandleW = g_tip_details_kernelbaseModuleHandle;
  if ( !g_tip_details_kernelbaseModuleHandle )
  {
    ModuleHandleW = GetModuleHandleW(L"kernelbase.dll");
    g_tip_details_kernelbaseModuleHandle = ModuleHandleW;
  }
  ProcAddress = GetProcAddress(ModuleHandleW, "TestCreate");
  `TestCreate'::`2'::s_pfnTestCreate = (__int64)ProcAddress;
  if ( ProcAddress )
LABEL_10:
    v5 = ((__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, __int64, _OWORD *))ProcAddress)(
           v15,
           0,
           v9,
           v8,
           v7,
           v6);
  else
    *v6 = 0;
  v12 = *(_QWORD *)(a1 + 232);
  if ( v12 )
  {
    LastError = GetLastError();
    TestClose(v12);
    SetLastError(LastError);
  }
  *(_QWORD *)(a1 + 232) = v5;
  *(_DWORD *)(a1 + 184) = 1;
  *a2 = *(_OWORD *)(a1 + 144);
  if ( pv )
    CoTaskMemFree(pv);
  if ( v4 )
    LeaveCriticalSection(v4);
  return a2;
}

```

## disassembly

```asm
0x180010050  mov     [rsp+arg_10], rbx
0x180010055  push    rbp
0x180010056  push    rsi
0x180010057  push    rdi
0x180010058  push    r12
0x18001005a  push    r13
0x18001005c  push    r14
0x18001005e  push    r15
0x180010060  sub     rsp, 890h
0x180010067  mov     rax, cs:__security_cookie
0x18001006e  xor     rax, rsp
0x180010071  mov     [rsp+8C8h+var_48], rax
0x180010079  mov     rbp, rdx
0x18001007c  mov     rdi, rcx
0x18001007f  lea     r14, [rcx+0C0h]
0x180010086  mov     rcx, r14; lpCriticalSection
0x180010089  call    cs:__imp_EnterCriticalSection
0x18001008f  xor     edx, edx; Val
0x180010091  mov     r8d, 802h; Size
0x180010097  lea     rcx, [rsp+8C8h+var_86A]; void *
0x18001009c  call    memset
0x1800100a1  xor     r15d, r15d
0x1800100a4  mov     [rsp+8C8h+pv], r15
0x1800100a9  mov     [rsp+8C8h+var_870], r15b
0x1800100ae  lea     rax, [rsp+8C8h+var_86F]
0x1800100b3  mov     [rsp+8C8h+var_68], rax
0x1800100bb  lea     rax, [rsp+8C8h+var_6F]
0x1800100c3  mov     [rsp+8C8h+var_58], rax
0x1800100cb  mov     [rsp+8C8h+var_86F], 80408040h
0x1800100d3  mov     [rsp+8C8h+var_86B], r15b
0x1800100d8  lea     rax, [rsp+8C8h+var_86A]
0x1800100dd  mov     [rsp+8C8h+var_60], rax
0x1800100e5  test    dword ptr [rdi+40h], 800h
0x1800100ec  jz      short loc_180010116
0x1800100ee  test    dword ptr [rdi+14h], 8000h
0x1800100f5  jnz     short loc_180010116
0x1800100f7  lea     rsi, [rdi+90h]
0x1800100fe  mov     r8d, 1
0x180010104  lea     rdx, [rsp+8C8h+pv]
0x180010109  mov     rcx, rdi
0x18001010c  call    ?serialize_data@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAPEBDAEAVwrite_buffer@tson@@W4serialize_options@23@@Z; tip2::details::shared_data<0,0,0>::serialize_data(tson::write_buffer &,tip2::details::serialize_options)
0x180010111  mov     r12, rax
0x180010114  jmp     short loc_180010120
0x180010116  lea     rsi, [rdi+90h]
0x18001011d  mov     r12, r15
0x180010120  mov     ebx, [rdi+14h]
0x180010123  movzx   r13d, byte ptr [rdi+20h]
0x180010128  mov     eax, [rdi+10h]
0x18001012b  mov     [rsp+8C8h+var_888], eax
0x18001012f  mov     rax, cs:?s_pfnTestCreate@?1??TestCreate@@9@4P6APEAUHTIPTEST__@@IW4TestRetrievalOptions@@W4TestStorage@@W4TestProperties@@PEBDPEAU_GUID@@@ZEA; HTIPTEST__ * (*`TestCreate'::`2'::s_pfnTestCreate)(uint,TestRetrievalOptions,TestStorage,TestProperties,char const *,_GUID *)
0x180010136  test    rax, rax
0x180010139  jnz     short loc_18001017F
0x18001013b  mov     rax, cs:g_tip_details_kernelbaseModuleHandle
0x180010142  test    rax, rax
0x180010145  jnz     short loc_18001015B
0x180010147  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x18001014e  call    cs:__imp_GetModuleHandleW
0x180010154  mov     cs:g_tip_details_kernelbaseModuleHandle, rax
0x18001015b  lea     rdx, aTestcreate; "TestCreate"
0x180010162  mov     rcx, rax; hModule
0x180010165  call    cs:__imp_GetProcAddress
0x18001016b  mov     cs:?s_pfnTestCreate@?1??TestCreate@@9@4P6APEAUHTIPTEST__@@IW4TestRetrievalOptions@@W4TestStorage@@W4TestProperties@@PEBDPEAU_GUID@@@ZEA, rax; HTIPTEST__ * (*`TestCreate'::`2'::s_pfnTestCreate)(uint,TestRetrievalOptions,TestStorage,TestProperties,char const *,_GUID *)
0x180010172  test    rax, rax
0x180010175  jnz     short loc_18001017F
0x180010177  xorps   xmm0, xmm0
0x18001017a  movups  xmmword ptr [rsi], xmm0
0x18001017d  jmp     short loc_18001019F
0x18001017f  mov     [rsp+8C8h+var_8A0], rsi
0x180010184  mov     [rsp+8C8h+var_8A8], r12
0x180010189  mov     r9d, ebx
0x18001018c  movzx   r8d, r13b
0x180010190  xor     edx, edx
0x180010192  mov     ecx, [rsp+8C8h+var_888]
0x180010196  call    cs:__guard_dispatch_icall_fptr
0x18001019c  mov     r15, rax
0x18001019f  mov     rsi, [rdi+0E8h]
0x1800101a6  test    rsi, rsi
0x1800101a9  jz      short loc_1800101C3
0x1800101ab  call    cs:__imp_GetLastError
0x1800101b1  mov     ebx, eax
0x1800101b3  mov     rcx, rsi
0x1800101b6  call    TestClose
0x1800101bb  mov     ecx, ebx; dwErrCode
0x1800101bd  call    cs:__imp_SetLastError
0x1800101c3  mov     [rdi+0E8h], r15
0x1800101ca  mov     dword ptr [rdi+0B8h], 1
0x1800101d4  movups  xmm0, xmmword ptr [rdi+90h]
0x1800101db  movups  xmmword ptr [rbp+0], xmm0
0x1800101df  mov     rcx, [rsp+8C8h+pv]; pv
0x1800101e4  test    rcx, rcx
0x1800101e7  jz      short loc_1800101EF
0x1800101e9  call    cs:__imp_CoTaskMemFree
0x1800101ef  test    r14, r14
0x1800101f2  jz      short loc_1800101FD
0x1800101f4  mov     rcx, r14; lpCriticalSection
0x1800101f7  call    cs:__imp_LeaveCriticalSection
0x1800101fd  mov     rax, rbp
0x180010200  mov     rcx, [rsp+8C8h+var_48]
0x180010208  xor     rcx, rsp; StackCookie
0x18001020b  call    __security_check_cookie
0x180010210  mov     rbx, [rsp+8C8h+arg_10]
0x180010218  add     rsp, 890h
0x18001021f  pop     r15
0x180010221  pop     r14
0x180010223  pop     r13
0x180010225  pop     r12
0x180010227  pop     rdi
0x180010228  pop     rsi
0x180010229  pop     rbp
0x18001022a  retn
```
