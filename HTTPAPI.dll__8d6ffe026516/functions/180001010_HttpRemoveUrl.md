# HttpRemoveUrl

- ea: `0x180001010`
- end: `0x180001123`
- name: `HttpRemoveUrl`
- size: `275`
- prototype: `ULONG __stdcall(HANDLE RequestQueueHandle, PCWSTR FullyQualifiedUrl)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x180001010`
- `0x180001130`
- `0x1800011f0`
- `0x18000b080`
- `0x18000c6c8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180001045`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180001045`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180001069`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180001069`

## pseudocode

```c
ULONG __stdcall HttpRemoveUrl(HANDLE RequestQueueHandle, PCWSTR FullyQualifiedUrl)
{
  int v2; // r8d
  _BOOL8 v5; // rdi
  _BOOL8 v6; // rbx
  ULONG UrlGroupForRequestQueue; // ebx
  __int64 v8; // rax
  ULONG v9; // eax
  HTTP_URL_GROUP_ID UrlGroupId; // [rsp+70h] [rbp+18h] BYREF

  UrlGroupId = 0;
  if ( (byte_1800126A3 & 4) != 0 )
    WPP_SF_qS((_DWORD)RequestQueueHandle, (_DWORD)FullyQualifiedUrl, v2, (__int64)RequestQueueHandle);
  EnterCriticalSection(&g_InitCritSec);
  v5 = dword_180012770 != 0;
  v6 = dword_180012768 != 0;
  LeaveCriticalSection(&g_InitCritSec);
  if ( v6 && v5 )
  {
    if ( !RequestQueueHandle )
      goto LABEL_15;
    if ( !FullyQualifiedUrl )
      goto LABEL_15;
    v8 = -1;
    do
      ++v8;
    while ( FullyQualifiedUrl[v8] );
    if ( v8 )
    {
      UrlGroupForRequestQueue = GetUrlGroupForRequestQueue(RequestQueueHandle, &UrlGroupId);
      if ( !UrlGroupForRequestQueue )
      {
        v9 = HttpRemoveUrlFromUrlGroup(UrlGroupId, FullyQualifiedUrl, 0);
        UrlGroupForRequestQueue = v9;
        if ( v9 )
        {
          if ( (byte_1800126A3 & 4) != 0 )
            WPP_SF_d(1050, 13, WPP_df74504d81f534d5550de2f15ba427fc_Traceguids, v9);
          UrlGroupForRequestQueue = 2;
        }
      }
    }
    else
    {
LABEL_15:
      UrlGroupForRequestQueue = 87;
    }
  }
  else
  {
    UrlGroupForRequestQueue = 1114;
  }
  if ( (byte_1800126A3 & 4) != 0 )
    WPP_SF_d(1050, 14, WPP_df74504d81f534d5550de2f15ba427fc_Traceguids, UrlGroupForRequestQueue);
  return UrlGroupForRequestQueue;
}

```

## disassembly

```asm
0x180001010  push    rbx
0x180001012  push    rbp
0x180001013  push    rsi
0x180001014  push    rdi
0x180001015  sub     rsp, 38h
0x180001019  mov     rsi, rdx
0x18000101c  mov     [rsp+58h+UrlGroupId], 0
0x180001025  mov     rbp, rcx
0x180001028  test    cs:byte_1800126A3, 4
0x18000102f  jz      short loc_18000103E
0x180001031  mov     r9, rcx
0x180001034  mov     [rsp+58h+var_38], rdx
0x180001039  call    WPP_SF_qS
0x18000103e  lea     rcx, g_InitCritSec; lpCriticalSection
0x180001045  call    cs:__imp_EnterCriticalSection
0x18000104b  xor     edi, edi
0x18000104d  lea     rcx, g_InitCritSec; lpCriticalSection
0x180001054  cmp     cs:dword_180012770, edi
0x18000105a  setnz   dil
0x18000105e  xor     ebx, ebx
0x180001060  cmp     cs:dword_180012768, ebx
0x180001066  setnz   bl
0x180001069  call    cs:__imp_LeaveCriticalSection
0x18000106f  test    edi, ebx
0x180001071  jnz     short loc_18000107A
0x180001073  mov     ebx, 45Ah
0x180001078  jmp     short loc_1800010F6
0x18000107a  test    rbp, rbp
0x18000107d  jz      short loc_1800010F1
0x18000107f  test    rsi, rsi
0x180001082  jz      short loc_1800010F1
0x180001084  mov     rax, 0FFFFFFFFFFFFFFFFh
0x18000108b  nop     dword ptr [rax+rax+00h]
0x180001090  inc     rax
0x180001093  cmp     word ptr [rsi+rax*2], 0
0x180001098  jnz     short loc_180001090
0x18000109a  test    rax, rax
0x18000109d  jz      short loc_1800010F1
0x18000109f  lea     rdx, [rsp+58h+UrlGroupId]
0x1800010a4  mov     rcx, rbp
0x1800010a7  call    GetUrlGroupForRequestQueue
0x1800010ac  mov     ebx, eax
0x1800010ae  test    eax, eax
0x1800010b0  jnz     short loc_1800010F6
0x1800010b2  mov     rcx, [rsp+58h+UrlGroupId]; UrlGroupId
0x1800010b7  xor     r8d, r8d; Flags
0x1800010ba  mov     rdx, rsi; pFullyQualifiedUrl
0x1800010bd  call    HttpRemoveUrlFromUrlGroup
0x1800010c2  mov     ebx, eax
0x1800010c4  test    eax, eax
0x1800010c6  jz      short loc_1800010F6
0x1800010c8  test    cs:byte_1800126A3, 4
0x1800010cf  jz      short loc_1800010EA
0x1800010d1  mov     edx, 0Dh
0x1800010d6  lea     r8, WPP_df74504d81f534d5550de2f15ba427fc_Traceguids
0x1800010dd  mov     ecx, 41Ah
0x1800010e2  mov     r9d, eax
0x1800010e5  call    WPP_SF_d
0x1800010ea  mov     ebx, 2
0x1800010ef  jmp     short loc_1800010F6
0x1800010f1  mov     ebx, 57h ; 'W'
0x1800010f6  test    cs:byte_1800126A3, 4
0x1800010fd  jz      short loc_180001118
0x1800010ff  mov     edx, 0Eh
0x180001104  lea     r8, WPP_df74504d81f534d5550de2f15ba427fc_Traceguids
0x18000110b  mov     ecx, 41Ah
0x180001110  mov     r9d, ebx
0x180001113  call    WPP_SF_d
0x180001118  mov     eax, ebx
0x18000111a  add     rsp, 38h
0x18000111e  pop     rdi
0x18000111f  pop     rsi
0x180001120  pop     rbp
0x180001121  pop     rbx
0x180001122  retn
```
