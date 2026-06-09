# GenerateSIDPublicKeyBlob(void *,uchar * *,ulong *)

- ea: `0x18000de80`
- end: `0x18000dfab`
- name: `?GenerateSIDPublicKeyBlob@@YAJPEAXPEAPEAEPEAK@Z`
- size: `299`
- prototype: `__int64 __fastcall(BCRYPT_KEY_HANDLE hKey, unsigned __int8 **, unsigned int *)`
- caller_count: `3`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800080e8`
- `0x18000e8a0`
- `0x1800189b8`

## callees

- `0x18000de80`
- `0x180010920`
- `0x180010950`
- `0x18001a450`

## import_xrefs

- `bcrypt!BCryptExportKey` at `0x18000dec7`
- `bcrypt!BCryptExportKey` at `0x18000df56`
- `bcrypt!BCryptExportKey` at `0x18000dec7`
- `bcrypt!BCryptExportKey` at `0x18000df56`

## string_xrefs

- `0x18000ded9`: `onecore\ds\security\keyman\sidkeyprov\common\sidkeysecagr.cxx`
- `0x18000df0e`: `onecore\ds\security\keyman\sidkeyprov\common\sidkeysecagr.cxx`
- `0x18000df68`: `onecore\ds\security\keyman\sidkeyprov\common\sidkeysecagr.cxx`

## pseudocode

```c
__int64 __fastcall GenerateSIDPublicKeyBlob(BCRYPT_KEY_HANDLE hKey, unsigned __int8 **a2, unsigned int *a3)
{
  NTSTATUS v6; // eax
  NTSTATUS v7; // ebx
  unsigned int v8; // ebx
  UCHAR *v9; // rdi
  NTSTATUS v10; // eax
  NTSTATUS v11; // ebx
  ULONG v12; // ecx
  ULONG pcbResult; // [rsp+78h] [rbp+20h] BYREF

  pcbResult = 0;
  v6 = BCryptExportKey(hKey, 0, L"PUBLICBLOB", 0, 0, &pcbResult, 0);
  v7 = v6;
  if ( v6 >= 0 )
  {
    v9 = (UCHAR *)SIDKeyProvAlloc(pcbResult);
    if ( v9 )
    {
      v10 = BCryptExportKey(hKey, 0, L"PUBLICBLOB", v9, pcbResult, &pcbResult, 0);
      v11 = v10;
      if ( v10 >= 0 )
      {
        v12 = pcbResult;
        v8 = 0;
        *a2 = v9;
        *a3 = v12;
      }
      else
      {
        SidKeyDebugTraceError(
          v10,
          "status",
          "onecore\\ds\\security\\keyman\\sidkeyprov\\common\\sidkeysecagr.cxx",
          0x280u);
        v8 = v11 | 0x10000000;
        SIDKeyProvFree(v9);
      }
    }
    else
    {
      v8 = -2147024882;
      SidKeyDebugTraceError(
        0x8007000E,
        "hr",
        "onecore\\ds\\security\\keyman\\sidkeyprov\\common\\sidkeysecagr.cxx",
        0x272u);
    }
  }
  else
  {
    SidKeyDebugTraceError(v6, "status", "onecore\\ds\\security\\keyman\\sidkeyprov\\common\\sidkeysecagr.cxx", 0x269u);
    return v7 | 0x10000000u;
  }
  return v8;
}

```

## disassembly

```asm
0x18000de80  mov     rax, rsp
0x18000de83  mov     [rax+8], rbx
0x18000de87  mov     [rax+10h], rbp
0x18000de8b  push    rsi
0x18000de8c  push    rdi
0x18000de8d  push    r14
0x18000de8f  sub     rsp, 40h
0x18000de93  mov     dword ptr [rax-28h], 0
0x18000de9a  mov     rsi, r8
0x18000de9d  mov     dword ptr [rax+20h], 0
0x18000dea4  lea     rax, [rax+20h]
0x18000dea8  mov     r14, rdx
0x18000deab  mov     [rsp+58h+pcbResult], rax; pcbResult
0x18000deb0  xor     r9d, r9d; pbOutput
0x18000deb3  mov     [rsp+58h+cbOutput], 0; cbOutput
0x18000debb  lea     r8, pszBlobType; "PUBLICBLOB"
0x18000dec2  xor     edx, edx; hExportKey
0x18000dec4  mov     rbp, rcx
0x18000dec7  call    cs:__imp_BCryptExportKey
0x18000decd  mov     ebx, eax
0x18000decf  test    eax, eax
0x18000ded1  jns     short loc_18000DEF7
0x18000ded3  mov     r9d, 269h; unsigned int
0x18000ded9  lea     r8, aOnecoreDsSecur_5; "onecore\\ds\\security\\keyman\\sidkeypr"...
0x18000dee0  lea     rdx, aStatus; "status"
0x18000dee7  mov     ecx, eax; unsigned int
0x18000dee9  call    ?SidKeyDebugTraceError@@YAXKPEBD0K@Z; SidKeyDebugTraceError(ulong,char const *,char const *,ulong)
0x18000deee  bts     ebx, 1Ch
0x18000def2  jmp     loc_18000DF96
0x18000def7  mov     ecx, [rsp+58h+arg_18]; unsigned __int64
0x18000defb  call    ?SIDKeyProvAlloc@@YAPEAX_K@Z; SIDKeyProvAlloc(unsigned __int64)
0x18000df00  mov     rdi, rax
0x18000df03  test    rax, rax
0x18000df06  jnz     short loc_18000DF2D
0x18000df08  mov     r9d, 272h; unsigned int
0x18000df0e  lea     r8, aOnecoreDsSecur_5; "onecore\\ds\\security\\keyman\\sidkeypr"...
0x18000df15  lea     rdx, aHr; "hr"
0x18000df1c  mov     ecx, 8007000Eh; unsigned int
0x18000df21  mov     ebx, 8007000Eh
0x18000df26  call    ?SidKeyDebugTraceError@@YAXKPEBD0K@Z; SidKeyDebugTraceError(ulong,char const *,char const *,ulong)
0x18000df2b  jmp     short loc_18000DF96
0x18000df2d  lea     rax, [rsp+58h+arg_18]
0x18000df32  mov     [rsp+58h+dwFlags], 0; dwFlags
0x18000df3a  mov     [rsp+58h+pcbResult], rax; pcbResult
0x18000df3f  lea     r8, pszBlobType; "PUBLICBLOB"
0x18000df46  mov     eax, [rsp+58h+arg_18]
0x18000df4a  mov     r9, rdi; pbOutput
0x18000df4d  xor     edx, edx; hExportKey
0x18000df4f  mov     [rsp+58h+cbOutput], eax; cbOutput
0x18000df53  mov     rcx, rbp; hKey
0x18000df56  call    cs:__imp_BCryptExportKey
0x18000df5c  mov     ebx, eax
0x18000df5e  test    eax, eax
0x18000df60  jns     short loc_18000DF8B
0x18000df62  mov     r9d, 280h; unsigned int
0x18000df68  lea     r8, aOnecoreDsSecur_5; "onecore\\ds\\security\\keyman\\sidkeypr"...
0x18000df6f  lea     rdx, aStatus; "status"
0x18000df76  mov     ecx, eax; unsigned int
0x18000df78  call    ?SidKeyDebugTraceError@@YAXKPEBD0K@Z; SidKeyDebugTraceError(ulong,char const *,char const *,ulong)
0x18000df7d  mov     rcx, rdi; lpMem
0x18000df80  bts     ebx, 1Ch
0x18000df84  call    ?SIDKeyProvFree@@YAXPEAX@Z; SIDKeyProvFree(void *)
0x18000df89  jmp     short loc_18000DF96
0x18000df8b  mov     ecx, [rsp+58h+arg_18]
0x18000df8f  xor     ebx, ebx
0x18000df91  mov     [r14], rdi
0x18000df94  mov     [rsi], ecx
0x18000df96  mov     rbp, [rsp+58h+arg_8]
0x18000df9b  mov     eax, ebx
0x18000df9d  mov     rbx, [rsp+58h+arg_0]
0x18000dfa2  add     rsp, 40h
0x18000dfa6  pop     r14
0x18000dfa8  pop     rdi
0x18000dfa9  pop     rsi
0x18000dfaa  retn
```
