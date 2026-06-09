# HttpCreateHttpHandle

- ea: `0x180003660`
- end: `0x18000374b`
- name: `HttpCreateHttpHandle`
- size: `235`
- prototype: `ULONG __stdcall(PHANDLE RequestQueueHandle, ULONG Reserved)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180003660`
- `0x180003e20`
- `0x18000b080`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000368e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000368e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800036b6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800036b6`

## pseudocode

```c
ULONG __stdcall HttpCreateHttpHandle(PHANDLE RequestQueueHandle, ULONG Reserved)
{
  _BOOL8 v4; // rdi
  _BOOL8 v5; // rbx
  ULONG v6; // ebx
  __int64 v8; // [rsp+78h] [rbp+20h] BYREF

  v8 = 0;
  EnterCriticalSection(&g_InitCritSec);
  v4 = dword_180012770 != 0;
  v5 = dword_180012768 != 0;
  LeaveCriticalSection(&g_InitCritSec);
  if ( v5 && v4 )
  {
    if ( RequestQueueHandle )
    {
      *RequestQueueHandle = 0;
      if ( Reserved )
      {
        v6 = 87;
      }
      else
      {
        v6 = HttpCreateRequestQueueEx(1u, 0, 0, 0, 0, 0, &v8);
        if ( !v6 )
          *RequestQueueHandle = (HANDLE)v8;
      }
    }
    else
    {
      v6 = 87;
    }
  }
  else
  {
    v6 = 1114;
  }
  if ( (byte_1800126A3 & 4) != 0 )
    WPP_SF_d(1050, 12, WPP_88109d8d3e5b32c3c016118f2408fbcf_Traceguids, v6);
  return v6;
}

```

## disassembly

```asm
0x180003660  mov     [rsp+arg_0], rbx
0x180003665  mov     [rsp+arg_8], rbp
0x18000366a  push    rsi
0x18000366b  push    rdi
0x18000366c  push    r14
0x18000366e  sub     rsp, 40h
0x180003672  mov     rsi, rcx
0x180003675  mov     [rsp+58h+arg_10], 1
0x18000367d  xor     r14d, r14d
0x180003680  lea     rcx, g_InitCritSec; lpCriticalSection
0x180003687  mov     [rsp+58h+arg_18], r14
0x18000368c  mov     ebp, edx
0x18000368e  call    cs:__imp_EnterCriticalSection
0x180003694  cmp     cs:dword_180012770, r14d
0x18000369b  lea     rcx, g_InitCritSec; lpCriticalSection
0x1800036a2  mov     edi, r14d
0x1800036a5  mov     ebx, r14d
0x1800036a8  setnz   dil
0x1800036ac  cmp     cs:dword_180012768, r14d
0x1800036b3  setnz   bl
0x1800036b6  call    cs:__imp_LeaveCriticalSection
0x1800036bc  test    edi, ebx
0x1800036be  jnz     short loc_1800036C7
0x1800036c0  mov     ebx, 45Ah
0x1800036c5  jmp     short loc_180003714
0x1800036c7  test    rsi, rsi
0x1800036ca  jnz     short loc_1800036D3
0x1800036cc  mov     ebx, 57h ; 'W'
0x1800036d1  jmp     short loc_180003714
0x1800036d3  mov     [rsi], r14
0x1800036d6  test    ebp, ebp
0x1800036d8  jz      short loc_1800036E1
0x1800036da  mov     ebx, 57h ; 'W'
0x1800036df  jmp     short loc_180003714
0x1800036e1  mov     ecx, [rsp+58h+arg_10]; int
0x1800036e5  lea     rax, [rsp+58h+arg_18]
0x1800036ea  mov     [rsp+58h+var_28], rax; __int64
0x1800036ef  xor     r9d, r9d; int
0x1800036f2  mov     [rsp+58h+var_30], r14; __int64
0x1800036f7  xor     r8d, r8d; __int64
0x1800036fa  xor     edx, edx; STRSAFE_LPCWSTR
0x1800036fc  mov     [rsp+58h+var_38], r14d; int
0x180003701  call    HttpCreateRequestQueueEx
0x180003706  mov     ebx, eax
0x180003708  test    eax, eax
0x18000370a  jnz     short loc_180003714
0x18000370c  mov     rax, [rsp+58h+arg_18]
0x180003711  mov     [rsi], rax
0x180003714  test    cs:byte_1800126A3, 4
0x18000371b  jz      short loc_180003736
0x18000371d  mov     edx, 0Ch
0x180003722  lea     r8, WPP_88109d8d3e5b32c3c016118f2408fbcf_Traceguids
0x180003729  mov     ecx, 41Ah
0x18000372e  mov     r9d, ebx
0x180003731  call    WPP_SF_d
0x180003736  mov     rbp, [rsp+58h+arg_8]
0x18000373b  mov     eax, ebx
0x18000373d  mov     rbx, [rsp+58h+arg_0]
0x180003742  add     rsp, 40h
0x180003746  pop     r14
0x180003748  pop     rdi
0x180003749  pop     rsi
0x18000374a  retn
```
