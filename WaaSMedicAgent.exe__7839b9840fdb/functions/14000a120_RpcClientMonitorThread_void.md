# RpcClientMonitorThread(void *)

- ea: `0x14000a120`
- end: `0x14000a30e`
- name: `?RpcClientMonitorThread@@YAKPEAX@Z`
- size: `494`
- prototype: `__int64 __fastcall(_WORD *Parameter)`
- caller_count: `0`
- callee_count: `9`
- tags: `service_task, installer_update`

## callees

- `0x14000198c`
- `0x140002a30`
- `0x140004290`
- `0x140004670`
- `0x14000885c`
- `0x140009920`
- `0x14000a120`
- `0x14000b470`
- `0x14000f3ec`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x14000a1d6`
- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x14000a1d6`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x14000a1e5`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x14000a1e5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000a2d8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000a2d8`

## string_xrefs

- `0x14000a2ba`: `Agent: Unexpected.  RPC Client should never release Mutex.`
- `0x14000a213`: `Agent: RPC Client no longer running`
- `0x14000a1fd`: `Agent: Unexpected result from WaitForSingleObject on Mutex.  %d`

## pseudocode

```c
__int64 __fastcall RpcClientMonitorThread(_WORD *Parameter)
{
  __int64 v1; // rsi
  __int64 v2; // r8
  int Sha256HashOfString; // eax
  unsigned int v4; // edi
  const WCHAR *v5; // r8
  char *MutexW; // rbx
  DWORD v7; // eax
  const struct _tlgProvider_t *v8; // rax
  const struct _tlgProvider_t *v9; // r10
  __int64 v10; // rax
  _QWORD v12[2]; // [rsp+38h] [rbp-39h] BYREF
  LPCWSTR lpName[2]; // [rsp+48h] [rbp-29h] BYREF
  __m128i si128; // [rsp+58h] [rbp-19h]
  UCHAR pbInput[16]; // [rsp+68h] [rbp-9h] BYREF
  __int64 v16; // [rsp+78h] [rbp+7h]
  __int64 v17; // [rsp+80h] [rbp+Fh]
  _QWORD *v18; // [rsp+88h] [rbp+17h]
  __int64 v19; // [rsp+90h] [rbp+1Fh]
  char *v20; // [rsp+98h] [rbp+27h]
  int v21; // [rsp+A0h] [rbp+2Fh]
  int v22; // [rsp+A4h] [rbp+33h]

  v12[1] = -2;
  *(_OWORD *)lpName = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(lpName[0]) = 0;
  *(_OWORD *)pbInput = 0;
  v16 = 0;
  v17 = 0;
  v1 = -1;
  v2 = -1;
  do
    ++v2;
  while ( Parameter[v2] );
  std::wstring::_Construct<1,unsigned short const *>(pbInput, Parameter);
  Sha256HashOfString = WaasMedic::GetSha256HashOfString(pbInput);
  v4 = Sha256HashOfString;
  if ( Sha256HashOfString >= 0 )
  {
    v5 = (const WCHAR *)lpName;
    if ( si128.m128i_i64[1] > 7uLL )
      v5 = lpName[0];
    MutexW = (char *)CreateMutexW(0, 1, v5);
    v7 = WaitForSingleObject(MutexW, 0xFFFFFFFF);
    if ( v7 )
    {
      if ( v7 == 128 )
      {
        LogLevelW(4u, L"Agent: RPC Client no longer running");
        v8 = WaasMedic::TelemetryProvider::Provider();
        v9 = v8;
        if ( *(_DWORD *)v8 > 5u )
        {
          v10 = *((_QWORD *)v8 + 3);
          if ( (*((_QWORD *)v9 + 2) & 0x400000000000LL) != 0 && (v10 & 0x400000000000LL) == v10 )
          {
            v12[0] = 0x1000000;
            do
              ++v1;
            while ( *(&g_pszCVBuff + v1) );
            v20 = &g_pszCVBuff;
            v21 = v1 + 1;
            v22 = 0;
            v18 = v12;
            v19 = 8;
            tlgWriteTransfer_EventWriteTransfer(v9, byte_140019C95, 0, 0, 4, pbInput);
          }
        }
        Shutdown(0);
      }
      else
      {
        LogLevelW(3u, L"Agent: Unexpected result from WaitForSingleObject on Mutex.  %d", v7);
      }
    }
    else
    {
      LogLevelW(3u, L"Agent: Unexpected.  RPC Client should never release Mutex.");
    }
    if ( (unsigned __int64)(MutexW - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
      CloseHandle(MutexW);
  }
  else
  {
    LogLevelW(2u, L"Failed to determine mutex name. hr = 0x%08x.", (unsigned int)Sha256HashOfString);
  }
  std::wstring::~wstring(lpName);
  return v4;
}

```

## disassembly

```asm
0x14000a120  mov     rax, rsp
0x14000a123  push    rbp
0x14000a124  push    rdi
0x14000a125  push    r14
0x14000a127  lea     rbp, [rax-5Fh]
0x14000a12b  sub     rsp, 0B0h
0x14000a132  mov     [rbp+57h+var_88], 0FFFFFFFFFFFFFFFEh
0x14000a13a  mov     [rax+10h], rbx
0x14000a13e  mov     [rax+18h], rsi
0x14000a142  mov     rax, cs:__security_cookie
0x14000a149  xor     rax, rsp
0x14000a14c  mov     [rbp+57h+var_20], rax
0x14000a150  xorps   xmm0, xmm0
0x14000a153  movups  xmmword ptr [rbp+57h+lpName], xmm0
0x14000a157  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x14000a15f  movdqu  [rbp+57h+var_70], xmm1
0x14000a164  xor     r14d, r14d
0x14000a167  mov     word ptr [rbp+57h+lpName], r14w
0x14000a16c  movups  xmmword ptr [rbp+57h+pbInput], xmm0
0x14000a170  mov     [rbp+57h+var_50], r14
0x14000a174  mov     [rbp+57h+var_48], r14
0x14000a178  or      rsi, 0FFFFFFFFFFFFFFFFh
0x14000a17c  mov     r8, rsi
0x14000a17f  inc     r8
0x14000a182  cmp     [rcx+r8*2], r14w
0x14000a187  jnz     short loc_14000A17F
0x14000a189  mov     rdx, rcx
0x14000a18c  lea     rcx, [rbp+57h+pbInput]
0x14000a190  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x14000a195  lea     rdx, [rbp+57h+lpName]
0x14000a199  lea     rcx, [rbp+57h+pbInput]; pbInput
0x14000a19d  call    ?GetSha256HashOfString@WaasMedic@@YAJV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV23@@Z; WaasMedic::GetSha256HashOfString(std::wstring,std::wstring &)
0x14000a1a2  mov     edi, eax
0x14000a1a4  test    eax, eax
0x14000a1a6  jns     short loc_14000A1C1
0x14000a1a8  mov     r8d, eax
0x14000a1ab  lea     rdx, aFailedToDeterm; "Failed to determine mutex name. hr = 0x"...
0x14000a1b2  mov     ecx, 2; unsigned __int8
0x14000a1b7  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x14000a1bc  jmp     loc_14000A2DF
0x14000a1c1  lea     r8, [rbp+57h+lpName]
0x14000a1c5  cmp     qword ptr [rbp+57h+var_70+8], 7
0x14000a1ca  cmova   r8, [rbp+57h+lpName]; lpName
0x14000a1cf  mov     edx, 1; bInitialOwner
0x14000a1d4  xor     ecx, ecx; lpMutexAttributes
0x14000a1d6  call    cs:__imp_CreateMutexW
0x14000a1dc  mov     rbx, rax
0x14000a1df  or      edx, 0FFFFFFFFh; dwMilliseconds
0x14000a1e2  mov     rcx, rax; hHandle
0x14000a1e5  call    cs:__imp_WaitForSingleObject
0x14000a1eb  test    eax, eax
0x14000a1ed  jz      loc_14000A2BA
0x14000a1f3  cmp     eax, 80h
0x14000a1f8  jz      short loc_14000A213
0x14000a1fa  mov     r8d, eax
0x14000a1fd  lea     rdx, aAgentUnexpecte; "Agent: Unexpected result from WaitForSi"...
0x14000a204  mov     ecx, 3; unsigned __int8
0x14000a209  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x14000a20e  jmp     loc_14000A2CB
0x14000a213  lea     rdx, aAgentRpcClient; "Agent: RPC Client no longer running"
0x14000a21a  mov     ecx, 4; unsigned __int8
0x14000a21f  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x14000a224  call    ?Provider@TelemetryProvider@WaasMedic@@SAPEBU_tlgProvider_t@@XZ; WaasMedic::TelemetryProvider::Provider(void)
0x14000a229  mov     r10, rax
0x14000a22c  mov     ecx, [rax]
0x14000a22e  cmp     ecx, 5
0x14000a231  jbe     short loc_14000A2B1
0x14000a233  mov     rax, [rax+18h]
0x14000a237  mov     rcx, [r10+10h]
0x14000a23b  mov     rdx, 400000000000h
0x14000a245  test    rdx, rcx
0x14000a248  jz      short loc_14000A2B1
0x14000a24a  mov     rcx, rax
0x14000a24d  and     rcx, rdx
0x14000a250  cmp     rcx, rax
0x14000a253  jnz     short loc_14000A2B1
0x14000a255  mov     [rbp+57h+var_90], 1000000h
0x14000a25d  lea     rax, ?g_pszCVBuff@@3PADA; char near * g_pszCVBuff
0x14000a264  inc     rsi
0x14000a267  cmp     [rax+rsi], r14b
0x14000a26b  jnz     short loc_14000A264
0x14000a26d  mov     [rbp+57h+var_30], rax
0x14000a271  lea     eax, [rsi+1]
0x14000a274  mov     [rbp+57h+var_28], eax
0x14000a277  mov     [rbp+57h+var_24], r14d
0x14000a27b  lea     rax, [rbp+57h+var_90]
0x14000a27f  mov     [rbp+57h+var_40], rax
0x14000a283  mov     [rbp+57h+var_38], 8
0x14000a28b  lea     rax, [rbp+57h+pbInput]
0x14000a28f  mov     [rsp+0C0h+var_98], rax
0x14000a294  mov     dword ptr [rsp+0C0h+var_A0], 4
0x14000a29c  xor     r9d, r9d
0x14000a29f  xor     r8d, r8d
0x14000a2a2  lea     rdx, byte_140019C95
0x14000a2a9  mov     rcx, r10
0x14000a2ac  call    _tlgWriteTransfer_EventWriteTransfer
0x14000a2b1  xor     ecx, ecx
0x14000a2b3  call    Shutdown
0x14000a2b8  jmp     short loc_14000A2CB
0x14000a2ba  lea     rdx, aAgentUnexpecte_0; "Agent: Unexpected.  RPC Client should n"...
0x14000a2c1  mov     ecx, 3; unsigned __int8
0x14000a2c6  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x14000a2cb  lea     rax, [rbx-1]
0x14000a2cf  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x14000a2d3  ja      short loc_14000A2DF
0x14000a2d5  mov     rcx, rbx; hObject
0x14000a2d8  call    cs:__imp_CloseHandle
0x14000a2de  nop
0x14000a2df  lea     rcx, [rbp+57h+lpName]; void *
0x14000a2e3  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14000a2e8  mov     eax, edi
0x14000a2ea  mov     rcx, [rbp+57h+var_20]
0x14000a2ee  xor     rcx, rsp; StackCookie
0x14000a2f1  call    __security_check_cookie
0x14000a2f6  lea     r11, [rsp+0C0h+var_10]
0x14000a2fe  mov     rbx, [r11+28h]
0x14000a302  mov     rsi, [r11+30h]
0x14000a306  mov     rsp, r11
0x14000a309  pop     r14
0x14000a30b  pop     rdi
0x14000a30c  pop     rbp
0x14000a30d  retn
```
