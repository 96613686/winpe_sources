# CConnectedUserStore::FinalRelease(void)

- ea: `0x18000be80`
- end: `0x18000c038`
- name: `?FinalRelease@CConnectedUserStore@@QEAAXXZ`
- size: `440`
- prototype: `void __fastcall(CConnectedUserStore *this, __int64, __int64)`
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x18000bde0`
- `0x1800108b0`

## callees

- `0x18000be80`
- `0x1800191ac`
- `0x18001b010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000bed2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000bef4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000bfe1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000c00e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000bed2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000bef4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000bfe1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000c00e`
- `ntdll!RtlFreeUnicodeString` at `0x18000bf02`
- `ntdll!RtlFreeUnicodeString` at `0x18000bf02`
- `ntdll!RtlDeleteCriticalSection` at `0x18000bf35`
- `ntdll!RtlDeleteCriticalSection` at `0x18000bf35`
- `SAMLIB!SamCloseHandle` at `0x18000bf11`
- `SAMLIB!SamCloseHandle` at `0x18000bf24`
- `SAMLIB!SamCloseHandle` at `0x18000bf11`
- `SAMLIB!SamCloseHandle` at `0x18000bf24`

## pseudocode

```c
void __fastcall CConnectedUserStore::FinalRelease(CConnectedUserStore *this, __int64 a2, __int64 a3)
{
  void *v4; // rcx
  __int64 v5; // rax
  void *v6; // rcx
  __int64 v7; // rcx
  __int64 v8; // rcx
  __int64 v9; // r8
  unsigned int i; // esi
  __int64 v11; // rdi
  __int64 v12; // rcx

  if ( WPP_GLOBAL_Control != (CIdentityProfileHandler *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
  {
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, a3, "CConnectedUserStore::FinalRelease");
  }
  v4 = (void *)*((_QWORD *)this + 14);
  if ( v4 )
  {
    if ( v4 != (void *)-1LL )
      CoTaskMemFree(v4);
    *((_QWORD *)this + 14) = 0;
    *((_DWORD *)this + 30) = 0;
  }
  v5 = *((_QWORD *)this + 21);
  if ( v5 )
  {
    if ( v5 != -1 )
    {
      for ( i = 0; i < *((_DWORD *)this + 44); ++i )
      {
        v11 = 32LL * i;
        v12 = *(_QWORD *)(v11 + *((_QWORD *)this + 21) + 24);
        if ( v12 )
        {
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
          *(_QWORD *)(v11 + *((_QWORD *)this + 21) + 24) = 0;
        }
        if ( *(_QWORD *)(v11 + *((_QWORD *)this + 21) + 16) )
        {
          CoTaskMemFree(*(LPVOID *)(v11 + *((_QWORD *)this + 21) + 16));
          *(_QWORD *)(v11 + *((_QWORD *)this + 21) + 16) = 0;
        }
      }
      CoTaskMemFree(*((LPVOID *)this + 21));
    }
    *((_QWORD *)this + 21) = 0;
    *((_DWORD *)this + 44) = 0;
  }
  v6 = (void *)*((_QWORD *)this + 11);
  if ( v6 )
  {
    CoTaskMemFree(v6);
    *((_QWORD *)this + 11) = 0;
  }
  RtlFreeUnicodeString((PUNICODE_STRING)((char *)this + 72));
  v7 = *((_QWORD *)this + 12);
  if ( v7 )
  {
    SamCloseHandle(v7);
    *((_QWORD *)this + 12) = 0;
  }
  v8 = *((_QWORD *)this + 13);
  if ( v8 )
  {
    SamCloseHandle(v8);
    *((_QWORD *)this + 13) = 0;
  }
  RtlDeleteCriticalSection((PRTL_CRITICAL_SECTION)((char *)this + 128));
  if ( WPP_GLOBAL_Control != (CIdentityProfileHandler *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
  {
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, v9, "CConnectedUserStore::FinalRelease");
  }
}

```

## disassembly

```asm
0x18000be80  push    rbx
0x18000be82  push    rbp
0x18000be83  push    rsi
0x18000be84  push    rdi
0x18000be85  push    r14
0x18000be87  push    r15
0x18000be89  sub     rsp, 38h
0x18000be8d  mov     rbx, rcx
0x18000be90  lea     r15, aCconnecteduser_14; "CConnectedUserStore::FinalRelease"
0x18000be97  mov     [rsp+68h+var_40], r15
0x18000be9c  xor     ebp, ebp
0x18000be9e  mov     [rsp+68h+var_48], rbp
0x18000bea3  lea     r14, WPP_GLOBAL_Control
0x18000beaa  mov     rcx, cs:WPP_GLOBAL_Control
0x18000beb1  cmp     rcx, r14
0x18000beb4  jz      short loc_18000BEC3
0x18000beb6  test    dword ptr [rcx+1Ch], 400h
0x18000bebd  jnz     loc_18000BFEC
0x18000bec3  mov     rcx, [rbx+70h]; pv
0x18000bec7  test    rcx, rcx
0x18000beca  jz      short loc_18000BEDF
0x18000becc  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18000bed0  jz      short loc_18000BED8
0x18000bed2  call    cs:__imp_CoTaskMemFree
0x18000bed8  mov     [rbx+70h], rbp
0x18000bedc  mov     [rbx+78h], ebp
0x18000bedf  mov     rax, [rbx+0A8h]
0x18000bee6  test    rax, rax
0x18000bee9  jnz     short loc_18000BF62
0x18000beeb  mov     rcx, [rbx+58h]; pv
0x18000beef  test    rcx, rcx
0x18000bef2  jz      short loc_18000BEFE
0x18000bef4  call    cs:__imp_CoTaskMemFree
0x18000befa  mov     [rbx+58h], rbp
0x18000befe  lea     rcx, [rbx+48h]; UnicodeString
0x18000bf02  call    cs:__imp_RtlFreeUnicodeString
0x18000bf08  mov     rcx, [rbx+60h]
0x18000bf0c  test    rcx, rcx
0x18000bf0f  jz      short loc_18000BF1B
0x18000bf11  call    cs:__imp_SamCloseHandle
0x18000bf17  mov     [rbx+60h], rbp
0x18000bf1b  mov     rcx, [rbx+68h]
0x18000bf1f  test    rcx, rcx
0x18000bf22  jz      short loc_18000BF2E
0x18000bf24  call    cs:__imp_SamCloseHandle
0x18000bf2a  mov     [rbx+68h], rbp
0x18000bf2e  lea     rcx, [rbx+80h]; CriticalSection
0x18000bf35  call    cs:__imp_RtlDeleteCriticalSection
0x18000bf3b  nop
0x18000bf3c  mov     rcx, cs:WPP_GLOBAL_Control
0x18000bf43  cmp     rcx, r14
0x18000bf46  jz      short loc_18000BF55
0x18000bf48  test    dword ptr [rcx+1Ch], 400h
0x18000bf4f  jnz     loc_18000C022
0x18000bf55  add     rsp, 38h
0x18000bf59  pop     r15
0x18000bf5b  pop     r14
0x18000bf5d  pop     rdi
0x18000bf5e  pop     rsi
0x18000bf5f  pop     rbp
0x18000bf60  pop     rbx
0x18000bf61  retn
0x18000bf62  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000bf66  jnz     short loc_18000BF7A
0x18000bf68  mov     [rbx+0A8h], rbp
0x18000bf6f  mov     [rbx+0B0h], ebp
0x18000bf75  jmp     loc_18000BEEB
0x18000bf7a  mov     esi, ebp
0x18000bf7c  cmp     [rbx+0B0h], ebp
0x18000bf82  jbe     short loc_18000BFDA
0x18000bf84  nop     dword ptr [rax+00h]
0x18000bf88  nop     dword ptr [rax+rax+00000000h]
0x18000bf90  mov     edi, esi
0x18000bf92  shl     rdi, 5
0x18000bf96  mov     rax, [rbx+0A8h]
0x18000bf9d  mov     rcx, [rdi+rax+18h]
0x18000bfa2  test    rcx, rcx
0x18000bfa5  jz      short loc_18000BFBF
0x18000bfa7  mov     rax, [rcx]
0x18000bfaa  mov     rax, [rax+10h]
0x18000bfae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bfb3  mov     rax, [rbx+0A8h]
0x18000bfba  mov     [rdi+rax+18h], rbp
0x18000bfbf  mov     rax, [rbx+0A8h]
0x18000bfc6  mov     rcx, [rdi+rax+10h]
0x18000bfcb  test    rcx, rcx
0x18000bfce  jnz     short loc_18000C002
0x18000bfd0  inc     esi
0x18000bfd2  cmp     esi, [rbx+0B0h]
0x18000bfd8  jb      short loc_18000BF90
0x18000bfda  mov     rcx, [rbx+0A8h]; pv
0x18000bfe1  call    cs:__imp_CoTaskMemFree
0x18000bfe7  jmp     loc_18000BF68
0x18000bfec  mov     edx, 0Ah
0x18000bff1  mov     r9, r15
0x18000bff4  mov     rcx, [rcx+10h]
0x18000bff8  call    WPP_SF_s
0x18000bffd  jmp     loc_18000BEC3
0x18000c002  mov     rcx, [rbx+0A8h]
0x18000c009  mov     rcx, [rdi+rcx+10h]; pv
0x18000c00e  call    cs:__imp_CoTaskMemFree
0x18000c014  mov     rax, [rbx+0A8h]
0x18000c01b  mov     [rdi+rax+10h], rbp
0x18000c020  jmp     short loc_18000BFD0
0x18000c022  mov     edx, 0Ch
0x18000c027  mov     r9, r15
0x18000c02a  mov     rcx, [rcx+10h]
0x18000c02e  call    WPP_SF_s
0x18000c033  jmp     loc_18000BF55
```
