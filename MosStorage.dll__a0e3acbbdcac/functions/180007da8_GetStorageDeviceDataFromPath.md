# GetStorageDeviceDataFromPath

- ea: `0x180007da8`
- end: `0x180007ef1`
- name: `GetStorageDeviceDataFromPath`
- size: `329`
- prototype: `__int64 __fastcall(LPCWCH lpString1, void *)`
- caller_count: `3`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x1800078d4`
- `0x180008c70`
- `0x180009be0`

## callees

- `0x180002802`
- `0x180006cd0`
- `0x1800071b0`
- `0x180007da8`
- `0x18000e7e0`
- `0x18000e7ec`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007e19`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007e19`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180007e0f`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180007e0f`
- `ZTrace_Maps!ZTraceReportOriginationNoThis` at `0x180007e43`
- `ZTrace_Maps!ZTraceReportOriginationNoThis` at `0x180007ea6`
- `ZTrace_Maps!ZTraceReportOriginationNoThis` at `0x180007e43`
- `ZTrace_Maps!ZTraceReportOriginationNoThis` at `0x180007ea6`
- `ZTrace_Maps!ZTraceReportPropagationNoThis` at `0x180007ed1`
- `ZTrace_Maps!ZTraceReportPropagationNoThis` at `0x180007ed1`

## string_xrefs

- `0x180007e3a`: `IsSamePath`
- `0x180007e9a`: `GetStorageDeviceDataFromPath`
- `0x180007ec8`: `GetStorageDeviceDataFromPath`

## pseudocode

```c
__int64 __fastcall GetStorageDeviceDataFromPath(LPCWCH lpString1, void *a2)
{
  int AllStorageDevices; // eax
  const WCHAR *i; // rbx
  int v6; // eax
  signed int LastError; // eax
  int v8; // r8d
  unsigned int v9; // eax
  unsigned int v10; // ebx
  void *Src[2]; // [rsp+30h] [rbp-6B8h] BYREF
  __int64 v13; // [rsp+40h] [rbp-6A8h]
  _BYTE v14[1084]; // [rsp+50h] [rbp-698h] BYREF
  _BYTE Buf1[604]; // [rsp+48Ch] [rbp-25Ch] BYREF

  *(_OWORD *)Src = 0;
  v13 = 0;
  memset_0(v14, 0, 0x670u);
  AllStorageDevices = GetAllStorageDevices(Src);
  if ( AllStorageDevices < 0 )
  {
    v8 = 222;
LABEL_19:
    v9 = ZTraceReportPropagationNoThis(AllStorageDevices, "GetStorageDeviceDataFromPath", v8);
    goto LABEL_20;
  }
  for ( i = (const WCHAR *)Src[0]; i != Src[1]; i += 824 )
  {
    v6 = CompareStringOrdinal(lpString1, -1, i + 6, -1, 1);
    if ( v6 )
    {
      if ( v6 == 2 )
      {
        memcpy_0(v14, i, 0x670u);
        break;
      }
    }
    else
    {
      LastError = GetLastError();
      if ( LastError )
      {
        if ( LastError > 0 )
          LastError = (unsigned __int16)LastError | 0x80070000;
      }
      else
      {
        LastError = -2143748092;
      }
      AllStorageDevices = ZTraceReportOriginationNoThis(LastError, "IsSamePath", 152);
      if ( AllStorageDevices < 0 )
      {
        v8 = 227;
        goto LABEL_19;
      }
    }
  }
  if ( !memcmp_0(Buf1, &GUID_NULL, 0x10u) )
  {
    v9 = ZTraceReportOriginationNoThis(-2147023728, "GetStorageDeviceDataFromPath", 236);
LABEL_20:
    v10 = v9;
    goto LABEL_21;
  }
  v10 = 0;
  memcpy_0(a2, v14, 0x670u);
LABEL_21:
  std::vector<_STORAGE_DEVICE_DATA>::~vector<_STORAGE_DEVICE_DATA>(Src);
  return v10;
}

```

## disassembly

```asm
0x180007da8  push    rbx
0x180007daa  push    rbp
0x180007dab  push    rsi
0x180007dac  push    rdi
0x180007dad  sub     rsp, 6C8h
0x180007db4  mov     rdi, rdx
0x180007db7  mov     rsi, rcx
0x180007dba  xorps   xmm0, xmm0
0x180007dbd  movdqu  xmmword ptr [rsp+6E8h+Src], xmm0
0x180007dc3  mov     [rsp+6E8h+var_6A8], 0
0x180007dcc  mov     ebp, 670h
0x180007dd1  mov     r8d, ebp; Size
0x180007dd4  xor     edx, edx; Val
0x180007dd6  lea     rcx, [rsp+6E8h+var_698]; void *
0x180007ddb  call    memset_0
0x180007de0  lea     rcx, [rsp+6E8h+Src]
0x180007de5  call    GetAllStorageDevices
0x180007dea  test    eax, eax
0x180007dec  js      loc_180007EC2
0x180007df2  mov     rbx, [rsp+6E8h+Src]
0x180007df7  jmp     short loc_180007E5D
0x180007df9  lea     r8, [rbx+0Ch]; lpString2
0x180007dfd  mov     [rsp+6E8h+bIgnoreCase], 1; bIgnoreCase
0x180007e05  or      r9d, 0FFFFFFFFh; cchCount2
0x180007e09  or      edx, r9d; cchCount1
0x180007e0c  mov     rcx, rsi; lpString1
0x180007e0f  call    cs:__imp_CompareStringOrdinal
0x180007e15  test    eax, eax
0x180007e17  jnz     short loc_180007E55
0x180007e19  call    cs:__imp_GetLastError
0x180007e1f  test    eax, eax
0x180007e21  jz      short loc_180007E2F
0x180007e23  jle     short loc_180007E34
0x180007e25  movzx   eax, ax
0x180007e28  or      eax, 80070000h
0x180007e2d  jmp     short loc_180007E34
0x180007e2f  mov     eax, 80390004h
0x180007e34  mov     r8d, 98h
0x180007e3a  lea     rdx, aIssamepath; "IsSamePath"
0x180007e41  mov     ecx, eax
0x180007e43  call    cs:__imp_?ZTraceReportOriginationNoThis@@YAJHPEBDH@Z; ZTraceReportOriginationNoThis(int,char const *,int)
0x180007e49  test    eax, eax
0x180007e4b  jns     short loc_180007E5A
0x180007e4d  mov     r8d, 0E3h
0x180007e53  jmp     short loc_180007EC8
0x180007e55  cmp     eax, 2
0x180007e58  jz      short loc_180007E66
0x180007e5a  add     rbx, rbp
0x180007e5d  cmp     rbx, [rsp+6E8h+Src+8]
0x180007e62  jnz     short loc_180007DF9
0x180007e64  jmp     short loc_180007E76
0x180007e66  lea     rcx, [rsp+6E8h+var_698]; void *
0x180007e6b  mov     rdx, rbx; Src
0x180007e6e  mov     r8, rbp; Size
0x180007e71  call    memcpy_0
0x180007e76  mov     r8d, 10h; Size
0x180007e7c  lea     rdx, GUID_NULL; Buf2
0x180007e83  lea     rcx, [rsp+6E8h+Buf1]; Buf1
0x180007e8b  call    memcmp_0
0x180007e90  test    eax, eax
0x180007e92  jnz     short loc_180007EAE
0x180007e94  mov     r8d, 0ECh
0x180007e9a  lea     rdx, aGetstoragedevi_0; "GetStorageDeviceDataFromPath"
0x180007ea1  mov     ecx, 80070490h
0x180007ea6  call    cs:__imp_?ZTraceReportOriginationNoThis@@YAJHPEBDH@Z; ZTraceReportOriginationNoThis(int,char const *,int)
0x180007eac  jmp     short loc_180007ED7
0x180007eae  xor     ebx, ebx
0x180007eb0  mov     rcx, rdi; void *
0x180007eb3  lea     rdx, [rsp+6E8h+var_698]; Src
0x180007eb8  mov     r8, rbp; Size
0x180007ebb  call    memcpy_0
0x180007ec0  jmp     short loc_180007ED9
0x180007ec2  mov     r8d, 0DEh
0x180007ec8  lea     rdx, aGetstoragedevi_0; "GetStorageDeviceDataFromPath"
0x180007ecf  mov     ecx, eax
0x180007ed1  call    cs:__imp_?ZTraceReportPropagationNoThis@@YAJHPEBDH@Z; ZTraceReportPropagationNoThis(int,char const *,int)
0x180007ed7  mov     ebx, eax
0x180007ed9  lea     rcx, [rsp+6E8h+Src]
0x180007ede  call    ??1?$vector@U_STORAGE_DEVICE_DATA@@V?$allocator@U_STORAGE_DEVICE_DATA@@@std@@@std@@QEAA@XZ; std::vector<_STORAGE_DEVICE_DATA>::~vector<_STORAGE_DEVICE_DATA>(void)
0x180007ee3  mov     eax, ebx
0x180007ee5  add     rsp, 6C8h
0x180007eec  pop     rdi
0x180007eed  pop     rsi
0x180007eee  pop     rbp
0x180007eef  pop     rbx
0x180007ef0  retn
```
