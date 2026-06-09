# Microsoft::Bluetooth::Services::BthServ::BthpFindFirstService(void *,_BLUETOOTH_SDP_SEARCH_PARAMS const *,_BLUETOOTH_SERVICE_RECORD *,_BTHSERV_QUERY_TYPE)

- ea: `0x180024738`
- end: `0x1800248a6`
- name: `?BthpFindFirstService@BthServ@Services@Bluetooth@Microsoft@@YAPEAXPEAXPEBU_BLUETOOTH_SDP_SEARCH_PARAMS@@PEAU_BLUETOOTH_SERVICE_RECORD@@W4_BTHSERV_QUERY_TYPE@@@Z`
- size: `366`
- prototype: `void *__high(void *, const struct _BLUETOOTH_SDP_SEARCH_PARAMS *, struct _BLUETOOTH_SERVICE_RECORD *, enum _BTHSERV_QUERY_TYPE)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x180022b34`

## callees

- `0x1800157d8`
- `0x180022f30`
- `0x1800231ac`
- `0x180024738`
- `0x180024ca8`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002476e`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800247a2`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002476e`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800247a2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002475c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180024794`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800247de`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002475c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180024794`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800247de`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800247ec`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800247ec`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002485f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002485f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180024886`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180024886`

## pseudocode

```c
Microsoft::Bluetooth::Services::BthServ *__fastcall Microsoft::Bluetooth::Services::BthServ::BthpFindFirstService(
        __int64 a1,
        __int64 a2,
        char *a3,
        int a4)
{
  HANDLE ProcessHeap; // rax
  void *v8; // rdx
  Microsoft::Bluetooth::Services::BthServ *v9; // rdi
  ULONG v10; // r14d
  DWORD L2CapSdpRecords; // ebx
  HANDLE v12; // rax
  Microsoft::Bluetooth::Services::BthServ *v13; // rax
  Microsoft::Bluetooth::Services::BthServ *v14; // rbp
  unsigned __int64 *v15; // rcx
  unsigned int *v16; // r9
  HANDLE v17; // rax
  struct _BLUETOOTH_SDP_RECORD *v18; // rsi
  struct _BLUETOOTH_SDP_RECORD *v19; // rax
  struct _BLUETOOTH_SERVICE_RECORD *v20; // r8
  Microsoft::Bluetooth::Services::BthServ *v21; // rsi
  __int64 v23; // [rsp+60h] [rbp+8h] BYREF

  v23 = a1;
  ProcessHeap = GetProcessHeap();
  v9 = (Microsoft::Bluetooth::Services::BthServ *)HeapAlloc(ProcessHeap, 8u, 0x18u);
  v10 = 512;
  L2CapSdpRecords = v9 == 0 ? 0xE : 0;
  while ( !L2CapSdpRecords || L2CapSdpRecords == 122 )
  {
    v12 = GetProcessHeap();
    v13 = (Microsoft::Bluetooth::Services::BthServ *)HeapAlloc(v12, 0, v10);
    v14 = v13;
    if ( !v13 )
    {
      L2CapSdpRecords = 14;
      break;
    }
    v15 = (unsigned __int64 *)(*(_QWORD *)(a2 + 8) + 8LL);
    LODWORD(v23) = 0;
    L2CapSdpRecords = BthServGetL2CapSdpRecords(v15, a4, (ULONG *)&v23, v13, v10);
    if ( !L2CapSdpRecords )
    {
      v18 = (Microsoft::Bluetooth::Services::BthServ *)((char *)v14 + (unsigned int)v23);
      *(_QWORD *)v9 = v14;
      *((_QWORD *)v9 + 2) = v18;
      *((_QWORD *)v9 + 1) = v14;
      if ( (*(_BYTE *)v14 & 0xF8) == 0x30 )
      {
        LODWORD(v23) = 0;
        v19 = Microsoft::Bluetooth::Services::BthServ::BthpInnerRecord(v14, v18, (unsigned __int32 *)&v23, v16);
        *((_QWORD *)v9 + 1) = v19;
        if ( v19 )
        {
          if ( v19 != v18 )
          {
            if ( (unsigned int)Microsoft::Bluetooth::Services::BthServ::BluetoothFindNextService(v9, a3, v20) )
            {
              v21 = v9;
              goto LABEL_18;
            }
            L2CapSdpRecords = GetLastError();
            goto LABEL_17;
          }
        }
      }
      break;
    }
    v17 = GetProcessHeap();
    HeapFree(v17, 0, v14);
    if ( L2CapSdpRecords != 122 )
      break;
    v10 = v23;
    if ( ((a4 - 1) & 0xFFFFFFFD) == 0 )
      a4 = 2;
  }
  v21 = 0;
  if ( !v9 )
    goto LABEL_18;
LABEL_17:
  Microsoft::Bluetooth::Services::BthServ::BluetoothFindServiceClose(v9, v8);
  v21 = 0;
LABEL_18:
  SetLastError(L2CapSdpRecords);
  return v21;
}

```

## disassembly

```asm
0x180024738  mov     [rsp+arg_8], rbx
0x18002473d  mov     [rsp+arg_10], rbp
0x180024742  mov     [rsp+arg_0], rcx
0x180024747  push    rsi
0x180024748  push    rdi
0x180024749  push    r13
0x18002474b  push    r14
0x18002474d  push    r15
0x18002474f  sub     rsp, 30h
0x180024753  mov     esi, r9d
0x180024756  mov     r15, r8
0x180024759  mov     r13, rdx
0x18002475c  call    cs:__imp_GetProcessHeap
0x180024762  mov     edx, 8; dwFlags
0x180024767  mov     rcx, rax; hHeap
0x18002476a  lea     r8d, [rdx+10h]; dwBytes
0x18002476e  call    cs:__imp_HeapAlloc
0x180024774  mov     rdi, rax
0x180024777  mov     r14d, 200h
0x18002477d  neg     rax
0x180024780  sbb     ebx, ebx
0x180024782  not     ebx
0x180024784  and     ebx, 0Eh
0x180024787  test    ebx, ebx
0x180024789  jz      short loc_180024794
0x18002478b  cmp     ebx, 7Ah ; 'z'
0x18002478e  jnz     loc_180024873
0x180024794  call    cs:__imp_GetProcessHeap
0x18002479a  mov     r8d, r14d; dwBytes
0x18002479d  xor     edx, edx; dwFlags
0x18002479f  mov     rcx, rax; hHeap
0x1800247a2  call    cs:__imp_HeapAlloc
0x1800247a8  mov     rbp, rax
0x1800247ab  test    rax, rax
0x1800247ae  jz      loc_18002486E
0x1800247b4  mov     rcx, [r13+8]
0x1800247b8  lea     r8, [rsp+58h+arg_0]
0x1800247bd  add     rcx, 8
0x1800247c1  mov     dword ptr [rsp+58h+arg_0], 0
0x1800247c9  mov     r9, rax
0x1800247cc  mov     [rsp+58h+var_38], r14d
0x1800247d1  mov     edx, esi
0x1800247d3  call    ?BthServGetL2CapSdpRecords@@YAKPEA_KW4_BTHSERV_QUERY_TYPE@@PEAKPEAEK@Z; BthServGetL2CapSdpRecords(unsigned __int64 *,_BTHSERV_QUERY_TYPE,ulong *,uchar *,ulong)
0x1800247d8  mov     ebx, eax
0x1800247da  test    eax, eax
0x1800247dc  jz      short loc_18002480F
0x1800247de  call    cs:__imp_GetProcessHeap
0x1800247e4  mov     r8, rbp; lpMem
0x1800247e7  xor     edx, edx; dwFlags
0x1800247e9  mov     rcx, rax; hHeap
0x1800247ec  call    cs:__imp_HeapFree
0x1800247f2  cmp     ebx, 7Ah ; 'z'
0x1800247f5  jnz     short loc_180024873
0x1800247f7  mov     r14d, dword ptr [rsp+58h+arg_0]
0x1800247fc  lea     ecx, [rsi-1]
0x1800247ff  test    ecx, 0FFFFFFFDh
0x180024805  jnz     short loc_180024787
0x180024807  lea     esi, [rbx-78h]
0x18002480a  jmp     loc_180024787
0x18002480f  mov     esi, dword ptr [rsp+58h+arg_0]
0x180024813  mov     rcx, rbp; this
0x180024816  add     rsi, rbp
0x180024819  mov     [rdi], rbp
0x18002481c  mov     [rdi+10h], rsi
0x180024820  mov     [rdi+8], rbp
0x180024824  mov     al, [rbp+0]
0x180024827  and     al, 0F8h
0x180024829  cmp     al, 30h ; '0'
0x18002482b  jnz     short loc_180024873
0x18002482d  lea     r8, [rsp+58h+arg_0]; void *
0x180024832  mov     dword ptr [rsp+58h+arg_0], 0
0x18002483a  mov     rdx, rsi; struct _BLUETOOTH_SDP_RECORD *
0x18002483d  call    ?BthpInnerRecord@BthServ@Services@Bluetooth@Microsoft@@YAPEAU_BLUETOOTH_SDP_RECORD@@PEAU5@PEAXPEAK@Z; Microsoft::Bluetooth::Services::BthServ::BthpInnerRecord(_BLUETOOTH_SDP_RECORD *,void *,ulong *)
0x180024842  mov     [rdi+8], rax
0x180024846  test    rax, rax
0x180024849  jz      short loc_180024873
0x18002484b  cmp     rax, rsi
0x18002484e  jz      short loc_180024873
0x180024850  mov     rdx, r15; void *
0x180024853  mov     rcx, rdi; this
0x180024856  call    ?BluetoothFindNextService@BthServ@Services@Bluetooth@Microsoft@@YAHPEAXPEAU_BLUETOOTH_SERVICE_RECORD@@@Z; Microsoft::Bluetooth::Services::BthServ::BluetoothFindNextService(void *,_BLUETOOTH_SERVICE_RECORD *)
0x18002485b  test    eax, eax
0x18002485d  jnz     short loc_180024869
0x18002485f  call    cs:__imp_GetLastError
0x180024865  mov     ebx, eax
0x180024867  jmp     short loc_18002487A
0x180024869  mov     rsi, rdi
0x18002486c  jmp     short loc_180024884
0x18002486e  mov     ebx, 0Eh
0x180024873  xor     esi, esi
0x180024875  test    rdi, rdi
0x180024878  jz      short loc_180024884
0x18002487a  mov     rcx, rdi; this
0x18002487d  call    ?BluetoothFindServiceClose@BthServ@Services@Bluetooth@Microsoft@@YAHPEAX@Z; Microsoft::Bluetooth::Services::BthServ::BluetoothFindServiceClose(void *)
0x180024882  xor     esi, esi
0x180024884  mov     ecx, ebx; dwErrCode
0x180024886  call    cs:__imp_SetLastError
0x18002488c  mov     rbx, [rsp+58h+arg_8]
0x180024891  mov     rax, rsi
0x180024894  mov     rbp, [rsp+58h+arg_10]
0x180024899  add     rsp, 30h
0x18002489d  pop     r15
0x18002489f  pop     r14
0x1800248a1  pop     r13
0x1800248a3  pop     rdi
0x1800248a4  pop     rsi
0x1800248a5  retn
```
