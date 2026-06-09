# Windows::Internal::Storage::Cloud::Common::SystemOps::PopulateServiceConfigW(SC_HANDLE__ *,wistd::unique_ptr<_QUERY_SERVICE_CONFIGW,wil::process_heap_deleter> &)

- ea: `0x1801bedf0`
- end: `0x1801beed3`
- name: `?PopulateServiceConfigW@SystemOps@Common@Cloud@Storage@Internal@Windows@@UEAAJPEAUSC_HANDLE__@@AEAV?$unique_ptr@U_QUERY_SERVICE_CONFIGW@@Uprocess_heap_deleter@wil@@@wistd@@@Z`
- size: `227`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x180046b44`
- `0x1801bedf0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801bee26`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801bee8d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801bee26`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801bee8d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1801bee58`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1801bee58`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1801bee47`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1801bee47`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x1801bee1c`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x1801bee83`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x1801bee1c`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x1801bee83`

## pseudocode

```c
signed int __fastcall Windows::Internal::Storage::Cloud::Common::SystemOps::PopulateServiceConfigW(
        __int64 a1,
        SC_HANDLE a2,
        wil::details **a3)
{
  signed int result; // eax
  DWORD v6; // ebp
  HANDLE ProcessHeap; // rax
  struct _QUERY_SERVICE_CONFIGW *v8; // rax
  wil::details *v9; // rdi
  void *v10; // rdx
  signed int LastError; // eax
  void *v12; // rdx
  unsigned int v13; // ebx
  wil::details *v14; // rcx
  SIZE_T dwBytes; // [rsp+58h] [rbp+20h] BYREF

  LODWORD(dwBytes) = 0;
  if ( QueryServiceConfigW(a2, 0, 0, (LPDWORD)&dwBytes) || (result = GetLastError(), result == 122) )
  {
    v6 = dwBytes;
    ProcessHeap = GetProcessHeap();
    v8 = (struct _QUERY_SERVICE_CONFIGW *)HeapAlloc(ProcessHeap, 8u, v6);
    v9 = (wil::details *)v8;
    if ( v8 )
    {
      LODWORD(dwBytes) = 0;
      if ( QueryServiceConfigW(a2, v8, v6, (LPDWORD)&dwBytes) )
      {
        v14 = *a3;
        *a3 = v9;
        if ( v14 )
          wil::details::FreeProcessHeap(v14, v10);
        return 0;
      }
      else
      {
        LastError = GetLastError();
        v13 = LastError;
        if ( LastError > 0 )
          v13 = (unsigned __int16)LastError | 0x80070000;
        wil::details::FreeProcessHeap(v9, v12);
        return v13;
      }
    }
    else
    {
      return -2147024882;
    }
  }
  else if ( result > 0 )
  {
    return (unsigned __int16)result | 0x80070000;
  }
  return result;
}

```

## disassembly

```asm
0x1801bedf0  mov     rax, rsp
0x1801bedf3  mov     [rax+8], rbx
0x1801bedf7  mov     [rax+10h], rbp
0x1801bedfb  push    rsi
0x1801bedfc  push    rdi
0x1801bedfd  push    r14
0x1801bedff  sub     rsp, 20h
0x1801bee03  mov     r14, rdx
0x1801bee06  mov     dword ptr [rax+20h], 0
0x1801bee0d  mov     rsi, r8
0x1801bee10  lea     r9, [rax+20h]; pcbBytesNeeded
0x1801bee14  mov     rcx, r14; hService
0x1801bee17  xor     r8d, r8d; cbBufSize
0x1801bee1a  xor     edx, edx; lpServiceConfig
0x1801bee1c  call    cs:__imp_QueryServiceConfigW
0x1801bee22  test    eax, eax
0x1801bee24  jnz     short loc_1801BEE43
0x1801bee26  call    cs:__imp_GetLastError
0x1801bee2c  cmp     eax, 7Ah ; 'z'
0x1801bee2f  jz      short loc_1801BEE43
0x1801bee31  test    eax, eax
0x1801bee33  jle     loc_1801BEEC0
0x1801bee39  movzx   eax, ax
0x1801bee3c  or      eax, 80070000h
0x1801bee41  jmp     short loc_1801BEEC0
0x1801bee43  mov     ebp, dword ptr [rsp+38h+dwBytes]
0x1801bee47  call    cs:__imp_GetProcessHeap
0x1801bee4d  mov     r8d, ebp; dwBytes
0x1801bee50  mov     edx, 8; dwFlags
0x1801bee55  mov     rcx, rax; hHeap
0x1801bee58  call    cs:__imp_HeapAlloc
0x1801bee5e  mov     rdi, rax
0x1801bee61  test    rax, rax
0x1801bee64  jnz     short loc_1801BEE6D
0x1801bee66  mov     eax, 8007000Eh
0x1801bee6b  jmp     short loc_1801BEEC0
0x1801bee6d  lea     r9, [rsp+38h+dwBytes]; pcbBytesNeeded
0x1801bee72  mov     dword ptr [rsp+38h+dwBytes], 0
0x1801bee7a  mov     r8d, ebp; cbBufSize
0x1801bee7d  mov     rdx, rdi; lpServiceConfig
0x1801bee80  mov     rcx, r14; hService
0x1801bee83  call    cs:__imp_QueryServiceConfigW
0x1801bee89  test    eax, eax
0x1801bee8b  jnz     short loc_1801BEEAE
0x1801bee8d  call    cs:__imp_GetLastError
0x1801bee93  mov     ebx, eax
0x1801bee95  test    eax, eax
0x1801bee97  jle     short loc_1801BEEA2
0x1801bee99  movzx   ebx, ax
0x1801bee9c  or      ebx, 80070000h
0x1801beea2  mov     rcx, rdi; this
0x1801beea5  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x1801beeaa  mov     eax, ebx
0x1801beeac  jmp     short loc_1801BEEC0
0x1801beeae  mov     rcx, [rsi]; this
0x1801beeb1  mov     [rsi], rdi
0x1801beeb4  test    rcx, rcx
0x1801beeb7  jz      short loc_1801BEEBE
0x1801beeb9  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x1801beebe  xor     eax, eax
0x1801beec0  mov     rbx, [rsp+38h+arg_0]
0x1801beec5  mov     rbp, [rsp+38h+arg_8]
0x1801beeca  add     rsp, 20h
0x1801beece  pop     r14
0x1801beed0  pop     rdi
0x1801beed1  pop     rsi
0x1801beed2  retn
```
