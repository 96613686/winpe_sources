# AddUserToHandle(void *,void *,ulong)

- ea: `0x180818410`
- end: `0x1808185c4`
- name: `?AddUserToHandle@@YAJPEAX0K@Z`
- size: `436`
- prototype: `HRESULT __fastcall(void *handle, void *userSid, unsigned int flags)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1808185cc`

## callees

- `0x1805117cc`
- `0x1806925ec`
- `0x180818410`
- `0x180819088`
- `0x180822eb8`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18081846e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18081852e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180818576`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180818597`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18081846e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18081852e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180818576`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180818597`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18081853c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180818584`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1808185a5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18081853c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180818584`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1808185a5`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18081847c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18081847c`
- `ntdll!NtQuerySecurityObject` at `0x180818443`
- `ntdll!NtQuerySecurityObject` at `0x1808184b7`
- `ntdll!NtQuerySecurityObject` at `0x180818443`
- `ntdll!NtQuerySecurityObject` at `0x1808184b7`
- `ntdll!NtSetSecurityObject` at `0x180818556`
- `ntdll!NtSetSecurityObject` at `0x180818556`
- `ntdll!RtlCreateSecurityDescriptor` at `0x1808184d9`
- `ntdll!RtlCreateSecurityDescriptor` at `0x1808184d9`

## pseudocode

```c
HRESULT __fastcall AddUserToHandle(void *handle, void *userSid, ACCESS_MASK flags)
{
  NTSTATUS v6; // eax
  unsigned int v8; // ebx
  HANDLE ProcessHeap; // rax
  WarningContext *v10; // rsi
  HRESULT v11; // ebx
  NTSTATUS v12; // eax
  int v13; // eax
  _ACL *v14; // rdi
  HANDLE v15; // rax
  NTSTATUS v16; // eax
  HRESULT v17; // eax
  _ACL *v18; // rbx
  HRESULT v19; // edi
  HANDLE v20; // rax
  _ACL *Dacl; // rbx
  HANDLE v22; // rax
  unsigned int requiredLength; // [rsp+30h] [rbp-38h] BYREF
  _SECURITY_DESCRIPTOR newSD; // [rsp+38h] [rbp-30h] BYREF
  void *retaddr; // [rsp+98h] [rbp+30h]
  bool exists; // [rsp+B8h] [rbp+50h] BYREF

  requiredLength = 0;
  v6 = NtQuerySecurityObject(handle, 4u, 0, 0, &requiredLength);
  if ( v6 == -1073741789 )
  {
    v8 = requiredLength;
    ProcessHeap = GetProcessHeap();
    v10 = (WarningContext *)HeapAlloc(ProcessHeap, 0, v8);
    if ( v10 )
    {
      v12 = NtQuerySecurityObject(handle, 4u, v10, requiredLength, &requiredLength);
      if ( v12 >= 0 && (memset(&newSD, 0, sizeof(newSD)), v12 = RtlCreateSecurityDescriptor(&newSD, 1u), v12 >= 0) )
      {
        exists = 0;
        v13 = BuildUserSD(v10, userSid, flags, &exists, &newSD);
        v11 = v13;
        if ( v13 >= 0 )
        {
          if ( exists || (v16 = NtSetSecurityObject(handle, 4u, &newSD), v16 >= 0) )
          {
            Dacl = newSD.Dacl;
            if ( newSD.Dacl )
            {
              v22 = GetProcessHeap();
              HeapFree(v22, 0, Dacl);
            }
            v11 = 0;
          }
          else
          {
            v17 = wil::details::in1diag0::Return_NtStatus(retaddr, v16);
            v18 = newSD.Dacl;
            v19 = v17;
            if ( newSD.Dacl )
            {
              v20 = GetProcessHeap();
              HeapFree(v20, 0, v18);
            }
            v11 = v19;
          }
        }
        else
        {
          wil::details::in1diag0::Return_Hr(retaddr, v13);
          v14 = newSD.Dacl;
          if ( newSD.Dacl )
          {
            v15 = GetProcessHeap();
            HeapFree(v15, 0, v14);
          }
        }
      }
      else
      {
        v11 = wil::details::in1diag0::Return_NtStatus(retaddr, v12);
      }
      DeallocateWarningContext(v10);
    }
    else
    {
      v11 = -2147024882;
      wil::details::in1diag0::Return_Hr(retaddr, -2147024882);
    }
    return v11;
  }
  else if ( v6 >= 0 )
  {
    return 0;
  }
  else
  {
    return wil::details::in1diag0::Return_NtStatus(retaddr, v6);
  }
}

```

## disassembly

```asm
0x180818410  push    rbp
0x180818412  push    rbx
0x180818413  push    rsi
0x180818414  push    rdi
0x180818415  push    r14
0x180818417  push    r15
0x180818419  mov     rbp, rsp
0x18081841c  sub     rsp, 68h
0x180818420  xor     r9d, r9d; Length
0x180818423  mov     [rbp+requiredLength], 0
0x18081842a  mov     r14d, flags
0x18081842d  lea     rax, [rbp+requiredLength]
0x180818431  mov     r15, userSid
0x180818434  mov     [rsp+68h+LengthNeeded], rax; LengthNeeded
0x180818439  xor     flags, flags; SecurityDescriptor
0x18081843c  mov     rdi, handle
0x18081843f  lea     edx, [r9+4]; SecurityInformation
0x180818443  call    cs:__imp_NtQuerySecurityObject
0x180818449  cmp     eax, 0C0000023h
0x18081844e  jz      short loc_18081846B
0x180818450  test    eax, eax
0x180818452  jns     short loc_180818464
0x180818454  mov     handle, [rbp+30h]; callerReturnAddress
0x180818458  mov     edx, eax; status
0x18081845a  call    ?Return_NtStatus@in1diag0@details@wil@@YAJPEAXJ@Z; wil::details::in1diag0::Return_NtStatus(void *,long)
0x18081845f  jmp     loc_1808185B7
0x180818464  xor     eax, eax
0x180818466  jmp     loc_1808185B7
0x18081846b  mov     ebx, [rbp+requiredLength]
0x18081846e  call    cs:__imp_GetProcessHeap
0x180818474  mov     flags, ebx; dwBytes
0x180818477  xor     edx, edx; dwFlags
0x180818479  mov     handle, rax; hHeap
0x18081847c  call    cs:__imp_HeapAlloc
0x180818482  mov     rsi, rax
0x180818485  test    rax, rax
0x180818488  jnz     short loc_18081849F
0x18081848a  mov     handle, [rbp+30h]; callerReturnAddress
0x18081848e  mov     ebx, 8007000Eh
0x180818493  mov     edx, ebx; hr
0x180818495  call    ?Return_Hr@in1diag0@details@wil@@YAXPEAXJ@Z; wil::details::in1diag0::Return_Hr(void *,long)
0x18081849a  jmp     loc_1808185B5
0x18081849f  mov     r9d, [rbp+requiredLength]; Length
0x1808184a3  lea     rax, [rbp+requiredLength]
0x1808184a7  mov     r8, rsi; SecurityDescriptor
0x1808184aa  mov     [rsp+68h+LengthNeeded], rax; LengthNeeded
0x1808184af  mov     edx, 4; SecurityInformation
0x1808184b4  mov     handle, rdi; Handle
0x1808184b7  call    cs:__imp_NtQuerySecurityObject
0x1808184bd  test    eax, eax
0x1808184bf  js      short loc_1808184E3
0x1808184c1  xor     eax, eax
0x1808184c3  lea     handle, [rbp+newSD]; SecurityDescriptor
0x1808184c7  xorps   xmm0, xmm0
0x1808184ca  mov     [rbp+newSD.Dacl], rax
0x1808184ce  movups  xmmword ptr [rbp+newSD.Revision], xmm0
0x1808184d2  lea     edx, [rax+1]; Revision
0x1808184d5  movups  xmmword ptr [rbp+newSD.Group], xmm0
0x1808184d9  call    cs:__imp_RtlCreateSecurityDescriptor
0x1808184df  test    eax, eax
0x1808184e1  jns     short loc_1808184F5
0x1808184e3  mov     handle, [rbp+30h]; callerReturnAddress
0x1808184e7  mov     edx, eax; status
0x1808184e9  call    ?Return_NtStatus@in1diag0@details@wil@@YAJPEAXJ@Z; wil::details::in1diag0::Return_NtStatus(void *,long)
0x1808184ee  mov     ebx, eax
0x1808184f0  jmp     loc_1808185AD
0x1808184f5  lea     rax, [rbp+newSD]
0x1808184f9  mov     [rbp+exists], 0
0x1808184fd  lea     r9, [rbp+exists]; exists
0x180818501  mov     [rsp+68h+LengthNeeded], rax; newSD
0x180818506  mov     flags, r14d; flags
0x180818509  mov     userSid, r15; userSid
0x18081850c  mov     handle, rsi; oldSD
0x18081850f  call    ?BuildUserSD@@YAJPEAX0KPEA_N0@Z; BuildUserSD(void *,void *,ulong,bool *,void *)
0x180818514  mov     ebx, eax
0x180818516  test    eax, eax
0x180818518  jns     short loc_180818544
0x18081851a  mov     handle, [rbp+30h]; callerReturnAddress
0x18081851e  mov     edx, eax; hr
0x180818520  call    ?Return_Hr@in1diag0@details@wil@@YAXPEAXJ@Z; wil::details::in1diag0::Return_Hr(void *,long)
0x180818525  mov     rdi, [rbp+newSD.Dacl]
0x180818529  test    rdi, rdi
0x18081852c  jz      short loc_1808185AD
0x18081852e  call    cs:__imp_GetProcessHeap
0x180818534  mov     r8, rdi; lpMem
0x180818537  xor     edx, edx; dwFlags
0x180818539  mov     handle, rax; hHeap
0x18081853c  call    cs:__imp_HeapFree
0x180818542  jmp     short loc_1808185AD
0x180818544  cmp     [rbp+exists], 0
0x180818548  jnz     short loc_18081858E
0x18081854a  lea     r8, [rbp+newSD]; SecurityDescriptor
0x18081854e  mov     edx, 4; SecurityInformation
0x180818553  mov     handle, rdi; Handle
0x180818556  call    cs:__imp_NtSetSecurityObject
0x18081855c  test    eax, eax
0x18081855e  jns     short loc_18081858E
0x180818560  mov     handle, [rbp+30h]; callerReturnAddress
0x180818564  mov     edx, eax; status
0x180818566  call    ?Return_NtStatus@in1diag0@details@wil@@YAJPEAXJ@Z; wil::details::in1diag0::Return_NtStatus(void *,long)
0x18081856b  mov     rbx, [rbp+newSD.Dacl]
0x18081856f  mov     edi, eax
0x180818571  test    rbx, rbx
0x180818574  jz      short loc_18081858A
0x180818576  call    cs:__imp_GetProcessHeap
0x18081857c  mov     r8, rbx; lpMem
0x18081857f  xor     edx, edx; dwFlags
0x180818581  mov     handle, rax; hHeap
0x180818584  call    cs:__imp_HeapFree
0x18081858a  mov     ebx, edi
0x18081858c  jmp     short loc_1808185AD
0x18081858e  mov     rbx, [rbp+newSD.Dacl]
0x180818592  test    rbx, rbx
0x180818595  jz      short loc_1808185AB
0x180818597  call    cs:__imp_GetProcessHeap
0x18081859d  mov     r8, rbx; lpMem
0x1808185a0  xor     edx, edx; dwFlags
0x1808185a2  mov     handle, rax; hHeap
0x1808185a5  call    cs:__imp_HeapFree
0x1808185ab  xor     ebx, ebx
0x1808185ad  mov     handle, rsi; context
0x1808185b0  call    ?DeallocateWarningContext@@YAHPEAUWarningContext@@@Z; DeallocateWarningContext(WarningContext *)
0x1808185b5  mov     eax, ebx
0x1808185b7  add     rsp, 68h
0x1808185bb  pop     r15
0x1808185bd  pop     r14
0x1808185bf  pop     rdi
0x1808185c0  pop     rsi
0x1808185c1  pop     rbx
0x1808185c2  pop     rbp
0x1808185c3  retn
```
