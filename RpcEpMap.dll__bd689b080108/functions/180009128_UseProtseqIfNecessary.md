# UseProtseqIfNecessary

- ea: `0x180009128`
- end: `0x180009268`
- name: `UseProtseqIfNecessary`
- size: `320`
- prototype: `__int64 __fastcall(unsigned __int16)`
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation, registry_config`

## callers

- `0x1800022b0`
- `0x1800081a4`

## callees

- `0x180006354`
- `0x180008724`
- `0x180008b80`
- `0x180009128`
- `0x18000a980`

## import_xrefs

- `RPCRT4!RpcServerUseProtseqEpExW` at `0x180009205`
- `RPCRT4!RpcServerUseProtseqEpExW` at `0x180009205`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009212`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009212`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180009220`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180009220`
- `ext-ms-win-core-winrt-remote-l1-1-0!GetLocalEndPointMapperCrossVmPipeName` at `0x1800091dc`
- `ext-ms-win-core-winrt-remote-l1-1-0!GetLocalEndPointMapperCrossVmPipeName` at `0x1800091dc`
- `ext-ms-win-core-winrt-remote-l1-1-0!RemoteWinRTActivation` at `0x1800091d2`
- `ext-ms-win-core-winrt-remote-l1-1-0!RemoteWinRTActivation` at `0x1800091d2`

## pseudocode

```c
__int64 __fastcall UseProtseqIfNecessary(unsigned __int16 a1)
{
  __int64 v1; // rdi
  __int64 v2; // rsi
  struct _ACL *Sd; // rax
  struct _ACL *v5; // rbx
  unsigned int v6; // ecx
  unsigned __int16 *LocalEndPointMapperCrossVmPipeName; // rax
  RPC_STATUS v8; // edi
  HANDLE ProcessHeap; // rax
  struct _RPC_POLICY Policy; // [rsp+30h] [rbp-38h] BYREF

  v1 = a1;
  *(_QWORD *)&Policy.Length = 12;
  Policy.NICFlags = fListenOnInternet != 0;
  if ( (unsigned __int16)(a1 - 1) <= 0x20u )
  {
    v2 = 3LL * a1;
    if ( *((_DWORD *)&gaProtseqInfo + 6 * a1) == 3 )
      return 0;
    if ( *((_DWORD *)&gaProtseqInfo + 6 * a1) != 4 )
    {
      if ( a1 == 16 )
      {
        Sd = CreateSd();
      }
      else
      {
        if ( a1 != 15 )
        {
          v5 = 0;
          goto LABEL_17;
        }
        Sd = (struct _ACL *)CreateNpSd();
      }
      v5 = Sd;
      v6 = 1721;
      if ( Sd )
        v6 = 0;
      if ( v6 )
        return v6;
      if ( (_WORD)v1 == 15 && (unsigned __int8)IsRemoteWinRTActivationPresent() && (unsigned int)RemoteWinRTActivation() )
      {
        LocalEndPointMapperCrossVmPipeName = (unsigned __int16 *)GetLocalEndPointMapperCrossVmPipeName();
LABEL_18:
        v8 = RpcServerUseProtseqEpExW(
               (RPC_WSTR)*(&gaProtseqInfo + 3 * v1 + 1),
               0x32u,
               LocalEndPointMapperCrossVmPipeName,
               v5,
               &Policy);
        if ( v5 )
        {
          ProcessHeap = GetProcessHeap();
          HeapFree(ProcessHeap, 0, v5);
        }
        v6 = 0;
        if ( v8 != 1740 )
          v6 = v8;
        if ( !v6 )
          *((_DWORD *)&gaProtseqInfo + 2 * v2) = 3;
        return v6;
      }
LABEL_17:
      LocalEndPointMapperCrossVmPipeName = (unsigned __int16 *)*(&gaProtseqInfo + 3 * v1 + 2);
      goto LABEL_18;
    }
  }
  return 1704;
}

```

## disassembly

```asm
0x180009128  mov     [rsp+arg_8], rbx
0x18000912d  mov     [rsp+arg_10], rbp
0x180009132  push    rsi
0x180009133  push    rdi
0x180009134  push    r14
0x180009136  sub     rsp, 50h
0x18000913a  mov     rax, cs:__security_cookie
0x180009141  xor     rax, rsp
0x180009144  mov     [rsp+68h+var_28], rax
0x180009149  xor     eax, eax
0x18000914b  movzx   edi, cx
0x18000914e  cmp     cs:?fListenOnInternet@@3HA, eax; int fListenOnInternet
0x180009154  mov     qword ptr [rsp+68h+var_38.Length], 0Ch
0x18000915d  setnz   al
0x180009160  mov     [rsp+68h+var_38.NICFlags], eax
0x180009164  lea     eax, [rdi-1]
0x180009167  cmp     ax, 20h ; ' '
0x18000916b  ja      loc_180009241
0x180009171  lea     rsi, [rdi+rdi*2]
0x180009175  lea     r14, ?gaProtseqInfo@@3PAUPROTSEQ_INFO@@A; PROTSEQ_INFO near * gaProtseqInfo
0x18000917c  cmp     dword ptr [r14+rsi*8], 3
0x180009181  jnz     short loc_18000918A
0x180009183  xor     eax, eax
0x180009185  jmp     loc_180009246
0x18000918a  cmp     dword ptr [r14+rsi*8], 4
0x18000918f  jz      loc_180009241
0x180009195  mov     ebp, 0Fh
0x18000919a  cmp     edi, 10h
0x18000919d  jnz     short loc_1800091A6
0x18000919f  call    CreateSd
0x1800091a4  jmp     short loc_1800091B0
0x1800091a6  cmp     di, bp
0x1800091a9  jnz     short loc_1800091E4
0x1800091ab  call    ?CreateNpSd@@YAPEAXXZ; CreateNpSd(void)
0x1800091b0  mov     rbx, rax
0x1800091b3  mov     ecx, 6B9h
0x1800091b8  xor     eax, eax
0x1800091ba  test    rbx, rbx
0x1800091bd  cmovnz  ecx, eax
0x1800091c0  test    ecx, ecx
0x1800091c2  jnz     short loc_18000923D
0x1800091c4  cmp     bp, di
0x1800091c7  jnz     short loc_1800091E6
0x1800091c9  call    IsRemoteWinRTActivationPresent
0x1800091ce  test    al, al
0x1800091d0  jz      short loc_1800091E6
0x1800091d2  call    cs:__imp_RemoteWinRTActivation
0x1800091d8  test    eax, eax
0x1800091da  jz      short loc_1800091E6
0x1800091dc  call    cs:__imp_GetLocalEndPointMapperCrossVmPipeName
0x1800091e2  jmp     short loc_1800091EB
0x1800091e4  xor     ebx, ebx
0x1800091e6  mov     rax, [r14+rsi*8+10h]
0x1800091eb  lea     rcx, [rsp+68h+var_38]
0x1800091f0  mov     r9, rbx; SecurityDescriptor
0x1800091f3  mov     [rsp+68h+Policy], rcx; Policy
0x1800091f8  mov     r8, rax; Endpoint
0x1800091fb  mov     rcx, [r14+rsi*8+8]; Protseq
0x180009200  mov     edx, 32h ; '2'; MaxCalls
0x180009205  call    cs:__imp_RpcServerUseProtseqEpExW
0x18000920b  mov     edi, eax
0x18000920d  test    rbx, rbx
0x180009210  jz      short loc_180009226
0x180009212  call    cs:__imp_GetProcessHeap
0x180009218  mov     r8, rbx; lpMem
0x18000921b  xor     edx, edx; dwFlags
0x18000921d  mov     rcx, rax; hHeap
0x180009220  call    cs:__imp_HeapFree
0x180009226  xor     ecx, ecx
0x180009228  cmp     edi, 6CCh
0x18000922e  cmovnz  ecx, edi
0x180009231  test    ecx, ecx
0x180009233  jnz     short loc_18000923D
0x180009235  mov     dword ptr [r14+rsi*8], 3
0x18000923d  mov     eax, ecx
0x18000923f  jmp     short loc_180009246
0x180009241  mov     eax, 6A8h
0x180009246  mov     rcx, [rsp+68h+var_28]
0x18000924b  xor     rcx, rsp; StackCookie
0x18000924e  call    __security_check_cookie
0x180009253  lea     r11, [rsp+68h+var_18]
0x180009258  mov     rbx, [r11+28h]
0x18000925c  mov     rbp, [r11+30h]
0x180009260  mov     rsp, r11
0x180009263  pop     r14
0x180009265  pop     rdi
0x180009266  pop     rsi
0x180009267  retn
```
