# DeploymentProgressHandler::Invoke(Windows::Foundation::IAsyncOperationWithProgress<Windows::Management::Deployment::DeploymentResult *,Windows::Management::Deployment::DeploymentProgress> *,ABI::Windows::Foundation::AsyncStatus)

- ea: `0x18001da10`
- end: `0x18001dec1`
- name: `?Invoke@DeploymentProgressHandler@@UEAAJPEAU?$IAsyncOperationWithProgress@PEAVDeploymentResult@Deployment@Management@Windows@@UDeploymentProgress@234@@Foundation@Windows@@W4AsyncStatus@34ABI@@@Z`
- size: `1201`
- prototype: ``
- caller_count: `0`
- callee_count: `13`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x180002a50`
- `0x1800065f8`
- `0x18000702c`
- `0x18000a358`
- `0x18000a3c0`
- `0x18000a440`
- `0x18000f8e4`
- `0x180012338`
- `0x180017348`
- `0x18001da10`
- `0x18001f3da`
- `0x18001f420`
- `0x180021010`

## import_xrefs

- `KERNEL32!FormatMessageW` at `0x18001dc5e`
- `KERNEL32!FormatMessageW` at `0x18001dc5e`
- `KERNEL32!SetEvent` at `0x18001de86`
- `KERNEL32!SetEvent` at `0x18001de86`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001dbb7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001dbb7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001db88`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001dd67`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001db88`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001dd67`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall DeploymentProgressHandler::Invoke(
        __int64 a1,
        int (__fastcall ***a2)(_QWORD, GUID *, __int64 *),
        int a3)
{
  int v6; // r15d
  struct JobHelper *JobHelper; // r12
  LPCWSTR v8; // rcx
  _QWORD *v9; // r9
  __int64 v10; // rdx
  int (__fastcall *v11)(_QWORD, GUID *, __int64 *); // rbx
  _QWORD *v12; // r9
  __int64 v13; // rdi
  __int64 (__fastcall *v14)(__int64, HSTRING *); // rbx
  PCWSTR StringRawBuffer; // rax
  _QWORD *v16; // rbx
  _QWORD *v17; // r9
  int *v18; // rdi
  _QWORD *v19; // rbx
  _QWORD *v20; // r9
  int v21; // eax
  __int64 v22; // rbx
  int v23; // edi
  __int64 v24; // rax
  __int64 v25; // r8
  __int64 v26; // rcx
  int v27; // eax
  __int64 v28; // rbx
  _QWORD *v29; // rdi
  __int64 v30; // rax
  __int64 v31; // rbx
  __int64 v32; // rax
  int v34; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v35; // [rsp+48h] [rbp-B8h] BYREF
  HSTRING string; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v37; // [rsp+58h] [rbp-A8h] BYREF
  _BYTE v38[32]; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v39[32]; // [rsp+80h] [rbp-80h] BYREF
  WCHAR Buffer[264]; // [rsp+A0h] [rbp-60h] BYREF

  v6 = 0;
  JobHelper = JobHelper::GetJobHelper();
  if ( a3 != 2 )
  {
    if ( a3 != 3 )
    {
      if ( a3 != 1 )
        goto LABEL_56;
      v27 = *(_DWORD *)(a1 + 168);
      if ( v27 == 1 )
      {
        v28 = std::wstring::wstring(v39, &dword_180022F6C);
        v29 = (_QWORD *)(a1 + 72);
        v30 = std::wstring::wstring(v38, a1 + 72);
        JobHelper::UpdateProgress(JobHelper, v30, 70, 100, 0, v28);
        v8 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (LPCWSTR)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
          goto LABEL_56;
        if ( *(_QWORD *)(a1 + 96) >= 8u )
          v29 = (_QWORD *)*v29;
        v10 = 16;
      }
      else
      {
        if ( v27 != 2 )
          goto LABEL_56;
        v31 = std::wstring::wstring(v39, &dword_180022F6C);
        v29 = (_QWORD *)(a1 + 72);
        v32 = std::wstring::wstring(v38, a1 + 72);
        JobHelper::UpdateProgress(JobHelper, v32, 100, 100, 0, v31);
        v8 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (LPCWSTR)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
          goto LABEL_56;
        if ( *(_QWORD *)(a1 + 96) >= 8u )
          v29 = (_QWORD *)*v29;
        v10 = 17;
      }
      v9 = v29;
LABEL_55:
      WPP_SF_S(*((_QWORD *)v8 + 2), v10, WPP_73de994102b632a5c4f5b05890cba07b_Traceguids, v9);
      goto LABEL_56;
    }
    v34 = 0;
    string = 0;
    v35 = 0;
    v37 = 0;
    v11 = **a2;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Detail::IVectorStatics>::InternalRelease(&v35);
    if ( v11(a2, &GUID_00000036_0000_0000_c000_000000000046, &v35) >= 0 )
    {
      if ( (*(int (__fastcall **)(__int64, int *))(*(_QWORD *)v35 + 64LL))(v35, &v34) >= 0 )
        *(_DWORD *)(a1 + 24) = v34;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v35 + 80LL))(v35);
      if ( WPP_GLOBAL_Control != (LPCWSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
      {
        v12 = (_QWORD *)(a1 + 72);
        if ( *(_QWORD *)(a1 + 96) >= 8u )
          v12 = (_QWORD *)*v12;
        WPP_SF_Sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          13,
          (unsigned int)WPP_73de994102b632a5c4f5b05890cba07b_Traceguids,
          (_DWORD)v12,
          *(_DWORD *)(a1 + 24));
      }
    }
    v6 = ((__int64 (__fastcall *)(int (__fastcall ***)(_QWORD, GUID *, __int64 *), __int64 *))(*a2)[10])(a2, &v37);
    if ( v6 < 0 )
    {
      memset_0(Buffer, 0, 0x208u);
      v18 = (int *)(a1 + 24);
      if ( FormatMessageW(0x1200u, 0, *(_DWORD *)(a1 + 24), 0x400u, Buffer, 0x104u, 0) )
      {
        v19 = (_QWORD *)(a1 + 32);
        std::wstring::assign(a1 + 32, Buffer);
        if ( WPP_GLOBAL_Control != (LPCWSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
        {
          if ( *(_QWORD *)(a1 + 56) >= 8u )
            v19 = (_QWORD *)*v19;
          v20 = (_QWORD *)(a1 + 72);
          if ( *(_QWORD *)(a1 + 96) >= 8u )
            v20 = (_QWORD *)*v20;
          WPP_SF_SS(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            15,
            (unsigned int)WPP_73de994102b632a5c4f5b05890cba07b_Traceguids,
            (_DWORD)v20,
            (__int64)v19);
        }
      }
    }
    else
    {
      v13 = v37;
      v14 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v37 + 48LL);
      WindowsDeleteString(string);
      string = 0;
      v6 = v14(v13, &string);
      StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
      v16 = (_QWORD *)(a1 + 32);
      std::wstring::assign(a1 + 32, StringRawBuffer);
      if ( WPP_GLOBAL_Control != (LPCWSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
      {
        if ( *(_QWORD *)(a1 + 56) >= 8u )
          v16 = (_QWORD *)*v16;
        v17 = (_QWORD *)(a1 + 72);
        if ( *(_QWORD *)(a1 + 96) >= 8u )
          v17 = (_QWORD *)*v17;
        WPP_SF_SS(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          14,
          (unsigned int)WPP_73de994102b632a5c4f5b05890cba07b_Traceguids,
          (_DWORD)v17,
          (__int64)v16);
      }
      v18 = (int *)(a1 + 24);
    }
    v21 = *(_DWORD *)(a1 + 168);
    if ( v21 == 1 )
    {
      v22 = std::wstring::wstring(v38, a1 + 32);
      v23 = *v18;
      v24 = std::wstring::wstring(v39, a1 + 72);
      v25 = 60;
    }
    else
    {
      if ( v21 != 2 )
      {
LABEL_38:
        v26 = v37;
        if ( v37 )
        {
          v37 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
        }
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Detail::IVectorStatics>::InternalRelease(&v35);
        WindowsDeleteString(string);
        goto LABEL_56;
      }
      v22 = std::wstring::wstring(v39, a1 + 32);
      v23 = *v18;
      v24 = std::wstring::wstring(v38, a1 + 72);
      v25 = 90;
    }
    JobHelper::UpdateProgress(JobHelper, v24, v25, 0, v23, v22);
    goto LABEL_38;
  }
  *(_DWORD *)(a1 + 24) = -2147009288;
  v8 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (LPCWSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
  {
    v9 = (_QWORD *)(a1 + 72);
    if ( *(_QWORD *)(a1 + 96) >= 8u )
      v9 = (_QWORD *)*v9;
    v10 = 12;
    goto LABEL_55;
  }
LABEL_56:
  SetEvent(*(HANDLE *)(a1 + 64));
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18001da10  mov     [rsp-8+arg_10], rbx
0x18001da15  mov     [rsp-8+arg_18], rsi
0x18001da1a  push    rbp
0x18001da1b  push    rdi
0x18001da1c  push    r12
0x18001da1e  push    r14
0x18001da20  push    r15
0x18001da22  lea     rbp, [rsp-1C0h]
0x18001da2a  sub     rsp, 2C0h
0x18001da31  mov     rax, cs:__security_cookie
0x18001da38  xor     rax, rsp
0x18001da3b  mov     [rbp+1E0h+var_30], rax
0x18001da42  mov     ebx, r8d
0x18001da45  mov     rdi, rdx
0x18001da48  mov     rsi, rcx
0x18001da4b  xor     r15d, r15d
0x18001da4e  call    ?GetJobHelper@JobHelper@@SAPEAV1@XZ; JobHelper::GetJobHelper(void)
0x18001da53  mov     r12, rax
0x18001da56  cmp     ebx, 2
0x18001da59  jnz     short loc_18001DA9B
0x18001da5b  mov     dword ptr [rsi+18h], 80073CF8h
0x18001da62  lea     r14, WPP_GLOBAL_Control
0x18001da69  mov     rcx, cs:WPP_GLOBAL_Control
0x18001da70  cmp     rcx, r14
0x18001da73  jz      loc_18001DE82
0x18001da79  test    byte ptr [rcx+1Ch], 1
0x18001da7d  jz      loc_18001DE82
0x18001da83  lea     r9, [rsi+48h]
0x18001da87  cmp     qword ptr [r9+18h], 8
0x18001da8c  jb      short loc_18001DA91
0x18001da8e  mov     r9, [r9]
0x18001da91  mov     edx, 0Ch
0x18001da96  jmp     loc_18001DE72
0x18001da9b  cmp     ebx, 3
0x18001da9e  jnz     loc_18001DD78
0x18001daa4  mov     [rsp+2E0h+var_2A0], r15d
0x18001daa9  mov     [rsp+2E0h+string], r15
0x18001daae  mov     [rsp+2E0h+var_298], r15
0x18001dab3  mov     [rsp+2E0h+var_288], r15
0x18001dab8  mov     rax, [rdi]
0x18001dabb  mov     rbx, [rax]
0x18001dabe  lea     rcx, [rsp+2E0h+var_298]
0x18001dac3  call    ?InternalRelease@?$ComPtr@UIVectorStatics@Detail@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Detail::IVectorStatics>::InternalRelease(void)
0x18001dac8  lea     r8, [rsp+2E0h+var_298]
0x18001dacd  lea     rdx, _GUID_00000036_0000_0000_c000_000000000046
0x18001dad4  mov     rcx, rdi
0x18001dad7  mov     rax, rbx
0x18001dada  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001dadf  lea     r14, WPP_GLOBAL_Control
0x18001dae6  test    eax, eax
0x18001dae8  js      short loc_18001DB58
0x18001daea  mov     rcx, [rsp+2E0h+var_298]
0x18001daef  mov     rax, [rcx]
0x18001daf2  lea     rdx, [rsp+2E0h+var_2A0]
0x18001daf7  mov     rax, [rax+40h]
0x18001dafb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001db00  test    eax, eax
0x18001db02  js      short loc_18001DB0B
0x18001db04  mov     eax, [rsp+2E0h+var_2A0]
0x18001db08  mov     [rsi+18h], eax
0x18001db0b  mov     rcx, [rsp+2E0h+var_298]
0x18001db10  mov     rax, [rcx]
0x18001db13  mov     rax, [rax+50h]
0x18001db17  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001db1c  mov     rcx, cs:WPP_GLOBAL_Control
0x18001db23  cmp     rcx, r14
0x18001db26  jz      short loc_18001DB58
0x18001db28  test    byte ptr [rcx+1Ch], 1
0x18001db2c  jz      short loc_18001DB58
0x18001db2e  mov     eax, [rsi+18h]
0x18001db31  lea     r9, [rsi+48h]
0x18001db35  cmp     qword ptr [r9+18h], 8
0x18001db3a  jb      short loc_18001DB3F
0x18001db3c  mov     r9, [r9]
0x18001db3f  mov     edx, 0Dh
0x18001db44  mov     dword ptr [rsp+2E0h+lpBuffer], eax
0x18001db48  lea     r8, WPP_73de994102b632a5c4f5b05890cba07b_Traceguids
0x18001db4f  mov     rcx, [rcx+10h]
0x18001db53  call    WPP_SF_Sd
0x18001db58  mov     rax, [rdi]
0x18001db5b  lea     rdx, [rsp+2E0h+var_288]
0x18001db60  mov     rcx, rdi
0x18001db63  mov     rax, [rax+50h]
0x18001db67  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001db6c  mov     r15d, eax
0x18001db6f  test    eax, eax
0x18001db71  js      loc_18001DC1F
0x18001db77  mov     rdi, [rsp+2E0h+var_288]
0x18001db7c  mov     rax, [rdi]
0x18001db7f  mov     rbx, [rax+30h]
0x18001db83  mov     rcx, [rsp+2E0h+string]; string
0x18001db88  call    cs:__imp_WindowsDeleteString
0x18001db8f  nop     dword ptr [rax+rax+00h]
0x18001db94  mov     [rsp+2E0h+string], 0
0x18001db9d  lea     rdx, [rsp+2E0h+string]
0x18001dba2  mov     rcx, rdi
0x18001dba5  mov     rax, rbx
0x18001dba8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001dbad  mov     r15d, eax
0x18001dbb0  xor     edx, edx; length
0x18001dbb2  mov     rcx, [rsp+2E0h+string]; string
0x18001dbb7  call    cs:__imp_WindowsGetStringRawBuffer
0x18001dbbe  nop     dword ptr [rax+rax+00h]
0x18001dbc3  lea     rbx, [rsi+20h]
0x18001dbc7  mov     rdx, rax
0x18001dbca  mov     rcx, rbx
0x18001dbcd  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z; std::wstring::assign(ushort const *)
0x18001dbd2  mov     rcx, cs:WPP_GLOBAL_Control
0x18001dbd9  cmp     rcx, r14
0x18001dbdc  jz      short loc_18001DC16
0x18001dbde  test    byte ptr [rcx+1Ch], 1
0x18001dbe2  jz      short loc_18001DC16
0x18001dbe4  cmp     qword ptr [rbx+18h], 8
0x18001dbe9  jb      short loc_18001DBEE
0x18001dbeb  mov     rbx, [rbx]
0x18001dbee  lea     r9, [rsi+48h]
0x18001dbf2  cmp     qword ptr [r9+18h], 8
0x18001dbf7  jb      short loc_18001DBFC
0x18001dbf9  mov     r9, [r9]
0x18001dbfc  mov     edx, 0Eh
0x18001dc01  mov     [rsp+2E0h+lpBuffer], rbx
0x18001dc06  lea     r8, WPP_73de994102b632a5c4f5b05890cba07b_Traceguids
0x18001dc0d  mov     rcx, [rcx+10h]
0x18001dc11  call    WPP_SF_SS
0x18001dc16  lea     rdi, [rsi+18h]
0x18001dc1a  jmp     loc_18001DCC2
0x18001dc1f  xor     edx, edx; Val
0x18001dc21  mov     r8d, 208h; Size
0x18001dc27  lea     rcx, [rbp+1E0h+Buffer]; void *
0x18001dc2b  call    memset_0
0x18001dc30  lea     rdi, [rsi+18h]
0x18001dc34  mov     [rsp+2E0h+Arguments], 0; Arguments
0x18001dc3d  mov     [rsp+2E0h+nSize], 104h; nSize
0x18001dc45  lea     rax, [rbp+1E0h+Buffer]
0x18001dc49  mov     [rsp+2E0h+lpBuffer], rax; lpBuffer
0x18001dc4e  mov     r9d, 400h; dwLanguageId
0x18001dc54  mov     r8d, [rdi]; dwMessageId
0x18001dc57  xor     edx, edx; lpSource
0x18001dc59  mov     ecx, 1200h; dwFlags
0x18001dc5e  call    cs:__imp_FormatMessageW
0x18001dc65  nop     dword ptr [rax+rax+00h]
0x18001dc6a  test    eax, eax
0x18001dc6c  jz      short loc_18001DCC2
0x18001dc6e  lea     rbx, [rsi+20h]
0x18001dc72  lea     rdx, [rbp+1E0h+Buffer]
0x18001dc76  mov     rcx, rbx
0x18001dc79  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z; std::wstring::assign(ushort const *)
0x18001dc7e  mov     rcx, cs:WPP_GLOBAL_Control
0x18001dc85  cmp     rcx, r14
0x18001dc88  jz      short loc_18001DCC2
0x18001dc8a  test    byte ptr [rcx+1Ch], 1
0x18001dc8e  jz      short loc_18001DCC2
0x18001dc90  cmp     qword ptr [rbx+18h], 8
0x18001dc95  jb      short loc_18001DC9A
0x18001dc97  mov     rbx, [rbx]
0x18001dc9a  lea     r9, [rsi+48h]
0x18001dc9e  cmp     qword ptr [r9+18h], 8
0x18001dca3  jb      short loc_18001DCA8
0x18001dca5  mov     r9, [r9]
0x18001dca8  mov     edx, 0Fh
0x18001dcad  mov     [rsp+2E0h+lpBuffer], rbx
0x18001dcb2  lea     r8, WPP_73de994102b632a5c4f5b05890cba07b_Traceguids
0x18001dcb9  mov     rcx, [rcx+10h]
0x18001dcbd  call    WPP_SF_SS
0x18001dcc2  mov     eax, [rsi+0A8h]
0x18001dcc8  cmp     eax, 1
0x18001dccb  jnz     short loc_18001DCF5
0x18001dccd  lea     rdx, [rsi+20h]
0x18001dcd1  lea     rcx, [rsp+2E0h+var_280]
0x18001dcd6  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18001dcdb  mov     rbx, rax
0x18001dcde  mov     edi, [rdi]
0x18001dce0  lea     rdx, [rsi+48h]
0x18001dce4  lea     rcx, [rbp+1E0h+var_260]
0x18001dce8  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18001dced  mov     r8d, 3Ch ; '<'
0x18001dcf3  jmp     short loc_18001DD20
0x18001dcf5  cmp     eax, 2
0x18001dcf8  jnz     short loc_18001DD38
0x18001dcfa  lea     rdx, [rsi+20h]
0x18001dcfe  lea     rcx, [rbp+1E0h+var_260]
0x18001dd02  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18001dd07  mov     rbx, rax
0x18001dd0a  mov     edi, [rdi]
0x18001dd0c  lea     rdx, [rsi+48h]
0x18001dd10  lea     rcx, [rsp+2E0h+var_280]
0x18001dd15  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18001dd1a  mov     r8d, 5Ah ; 'Z'
0x18001dd20  mov     qword ptr [rsp+2E0h+nSize], rbx
0x18001dd25  mov     dword ptr [rsp+2E0h+lpBuffer], edi
0x18001dd29  xor     r9d, r9d
0x18001dd2c  mov     rdx, rax
0x18001dd2f  mov     rcx, r12
0x18001dd32  call    ?UpdateProgress@JobHelper@@QEAAJV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4JobStatus@@KK0@Z; JobHelper::UpdateProgress(std::wstring,JobStatus,ulong,ulong,std::wstring)
0x18001dd37  nop
0x18001dd38  mov     rcx, [rsp+2E0h+var_288]
0x18001dd3d  test    rcx, rcx
0x18001dd40  jz      short loc_18001DD58
0x18001dd42  mov     [rsp+2E0h+var_288], 0
0x18001dd4b  mov     rax, [rcx]
0x18001dd4e  mov     rax, [rax+10h]
0x18001dd52  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001dd57  nop
0x18001dd58  lea     rcx, [rsp+2E0h+var_298]
0x18001dd5d  call    ?InternalRelease@?$ComPtr@UIVectorStatics@Detail@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Detail::IVectorStatics>::InternalRelease(void)
0x18001dd62  mov     rcx, [rsp+2E0h+string]; string
0x18001dd67  call    cs:__imp_WindowsDeleteString
0x18001dd6e  nop     dword ptr [rax+rax+00h]
0x18001dd73  jmp     loc_18001DE82
0x18001dd78  cmp     ebx, 1
0x18001dd7b  jnz     loc_18001DE82
0x18001dd81  mov     eax, [rsi+0A8h]
0x18001dd87  cmp     eax, ebx
0x18001dd89  jnz     short loc_18001DE00
0x18001dd8b  lea     rdx, dword_180022F6C
0x18001dd92  lea     rcx, [rbp+1E0h+var_260]
0x18001dd96  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x18001dd9b  mov     rbx, rax
0x18001dd9e  lea     rdi, [rsi+48h]
0x18001dda2  mov     rdx, rdi
0x18001dda5  lea     rcx, [rsp+2E0h+var_280]
0x18001ddaa  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18001ddaf  mov     qword ptr [rsp+2E0h+nSize], rbx
0x18001ddb4  mov     dword ptr [rsp+2E0h+lpBuffer], r15d
0x18001ddb9  mov     r9d, 64h ; 'd'
0x18001ddbf  lea     r8d, [r9-1Eh]
0x18001ddc3  mov     rdx, rax
0x18001ddc6  mov     rcx, r12
0x18001ddc9  call    ?UpdateProgress@JobHelper@@QEAAJV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4JobStatus@@KK0@Z; JobHelper::UpdateProgress(std::wstring,JobStatus,ulong,ulong,std::wstring)
0x18001ddce  lea     r14, WPP_GLOBAL_Control
0x18001ddd5  mov     rcx, cs:WPP_GLOBAL_Control
0x18001dddc  cmp     rcx, r14
0x18001dddf  jz      loc_18001DE82
0x18001dde5  test    byte ptr [rcx+1Ch], 1
0x18001dde9  jz      loc_18001DE82
0x18001ddef  cmp     qword ptr [rdi+18h], 8
0x18001ddf4  jb      short loc_18001DDF9
0x18001ddf6  mov     rdi, [rdi]
0x18001ddf9  mov     edx, 10h
0x18001ddfe  jmp     short loc_18001DE6F
0x18001de00  cmp     eax, 2
0x18001de03  jnz     short loc_18001DE82
0x18001de05  lea     rdx, dword_180022F6C
0x18001de0c  lea     rcx, [rbp+1E0h+var_260]
0x18001de10  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x18001de15  mov     rbx, rax
0x18001de18  lea     rdi, [rsi+48h]
0x18001de1c  mov     rdx, rdi
0x18001de1f  lea     rcx, [rsp+2E0h+var_280]
0x18001de24  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18001de29  mov     qword ptr [rsp+2E0h+nSize], rbx
0x18001de2e  mov     dword ptr [rsp+2E0h+lpBuffer], r15d
0x18001de33  mov     r8d, 64h ; 'd'
0x18001de39  mov     r9d, r8d
0x18001de3c  mov     rdx, rax
0x18001de3f  mov     rcx, r12
0x18001de42  call    ?UpdateProgress@JobHelper@@QEAAJV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4JobStatus@@KK0@Z; JobHelper::UpdateProgress(std::wstring,JobStatus,ulong,ulong,std::wstring)
0x18001de47  lea     r14, WPP_GLOBAL_Control
0x18001de4e  mov     rcx, cs:WPP_GLOBAL_Control
0x18001de55  cmp     rcx, r14
0x18001de58  jz      short loc_18001DE82
0x18001de5a  test    byte ptr [rcx+1Ch], 1
0x18001de5e  jz      short loc_18001DE82
0x18001de60  cmp     qword ptr [rdi+18h], 8
0x18001de65  jb      short loc_18001DE6A
0x18001de67  mov     rdi, [rdi]
0x18001de6a  mov     edx, 11h
0x18001de6f  mov     r9, rdi
0x18001de72  lea     r8, WPP_73de994102b632a5c4f5b05890cba07b_Traceguids
0x18001de79  mov     rcx, [rcx+10h]
0x18001de7d  call    WPP_SF_S
0x18001de82  mov     rcx, [rsi+40h]; hEvent
0x18001de86  call    cs:__imp_SetEvent
0x18001de8d  nop     dword ptr [rax+rax+00h]
0x18001de92  mov     eax, r15d
0x18001de95  mov     rcx, [rbp+1E0h+var_30]
0x18001de9c  xor     rcx, rsp; StackCookie
0x18001de9f  call    __security_check_cookie
0x18001dea4  lea     r11, [rsp+2E0h+var_20]
0x18001deac  mov     rbx, [r11+40h]
0x18001deb0  mov     rsi, [r11+48h]
0x18001deb4  mov     rsp, r11
0x18001deb7  pop     r15
0x18001deb9  pop     r14
0x18001debb  pop     r12
0x18001debd  pop     rdi
0x18001debe  pop     rbp
0x18001debf  retn
```
