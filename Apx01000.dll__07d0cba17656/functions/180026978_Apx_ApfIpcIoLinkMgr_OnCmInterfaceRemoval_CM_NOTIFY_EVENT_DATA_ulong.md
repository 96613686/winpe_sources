# Apx::ApfIpcIoLinkMgr::OnCmInterfaceRemoval(_CM_NOTIFY_EVENT_DATA *,ulong)

- ea: `0x180026978`
- end: `0x180026b4e`
- name: `?OnCmInterfaceRemoval@ApfIpcIoLinkMgr@Apx@@AEAAXPEAU_CM_NOTIFY_EVENT_DATA@@K@Z`
- size: `470`
- prototype: `void __fastcall(signed __int64 this, struct _CM_NOTIFY_EVENT_DATA *, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: `reparse_path, registry_config`

## callers

- `0x180026fb0`

## callees

- `0x1800027c8`
- `0x18000a12c`
- `0x18000b6e0`
- `0x180026978`
- `0x180027068`
- `0x180027138`
- `0x18002a010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180026af9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180026af9`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800269c4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800269c4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180026ad9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180026ad9`
- `api-ms-win-devices-config-l1-1-1!CM_Unregister_Notification` at `0x180026b08`
- `api-ms-win-devices-config-l1-1-1!CM_Unregister_Notification` at `0x180026b08`
- `api-ms-win-core-io-l1-1-0!CancelIoEx` at `0x180026aca`
- `api-ms-win-core-io-l1-1-0!CancelIoEx` at `0x180026aca`

## pseudocode

```c
void __fastcall Apx::ApfIpcIoLinkMgr::OnCmInterfaceRemoval(
        signed __int64 this,
        struct _CM_NOTIFY_EVENT_DATA *a2,
        unsigned int a3)
{
  __int64 v6; // r8
  __int64 SymLinkFromCmEventData; // r10
  unsigned __int16 *v8; // rax
  __int64 v9; // r8
  int v10; // edx
  int v11; // ecx
  void *v12; // rcx
  __int64 v13; // r8
  void *v14; // rcx

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 42, &WPP_e6720f2ec66938db1e8abec7a65481bb_Traceguids);
  }
  EnterCriticalSection((LPCRITICAL_SECTION)(this + 16));
  SymLinkFromCmEventData = Apx::ApfHelper::GetSymLinkFromCmEventData(1u, (__int64)a2, a3);
  if ( SymLinkFromCmEventData )
  {
    v8 = (unsigned __int16 *)(this + 118);
    v9 = SymLinkFromCmEventData - (this + 118);
    do
    {
      v10 = *(unsigned __int16 *)((char *)v8 + v9);
      v11 = *v8 - v10;
      if ( v11 )
        break;
      ++v8;
    }
    while ( v10 );
    if ( v11 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && *((char *)WPP_GLOBAL_Control + 28) < 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        WPP_SF_qSS(*((_QWORD *)WPP_GLOBAL_Control + 2), this + 118, SymLinkFromCmEventData);
      }
    }
    else
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && *((char *)WPP_GLOBAL_Control + 28) < 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 45, v9, ~this);
      }
      memset_0((void *)(this + 118), 0, 0x20Au);
      v12 = *(void **)(this + 88);
      if ( v12 )
      {
        CancelIoEx(v12, 0);
        v14 = *(void **)(this + 88);
        if ( v14 )
        {
          CloseHandle(v14);
          *(_QWORD *)(this + 88) = 0;
        }
        LOBYTE(v13) = 1;
        (*(void (__fastcall **)(_QWORD, _QWORD, __int64))(this + 56))(*(_QWORD *)(this + 64), 0, v13);
      }
    }
  }
  else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
         && *((char *)WPP_GLOBAL_Control + 28) < 0
         && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 43, v6, ~this);
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)(this + 16));
  if ( *(_QWORD *)(this + 104) )
  {
    CM_Unregister_Notification();
    *(_QWORD *)(this + 104) = 0;
  }
  *(_BYTE *)(this + 117) = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 46, &WPP_e6720f2ec66938db1e8abec7a65481bb_Traceguids);
  }
}

```

## disassembly

```asm
0x180026978  push    rbx
0x18002697a  push    rbp
0x18002697b  push    rsi
0x18002697c  push    rdi
0x18002697d  push    r14
0x18002697f  sub     rsp, 30h
0x180026983  mov     edi, r8d
0x180026986  mov     rsi, rdx
0x180026989  mov     rbx, rcx
0x18002698c  mov     rcx, cs:WPP_GLOBAL_Control
0x180026993  lea     r14, WPP_GLOBAL_Control
0x18002699a  cmp     rcx, r14
0x18002699d  jz      short loc_1800269C0
0x18002699f  test    byte ptr [rcx+1Ch], 1
0x1800269a3  jz      short loc_1800269C0
0x1800269a5  cmp     byte ptr [rcx+19h], 5
0x1800269a9  jb      short loc_1800269C0
0x1800269ab  mov     rcx, [rcx+10h]
0x1800269af  lea     r8, WPP_e6720f2ec66938db1e8abec7a65481bb_Traceguids
0x1800269b6  mov     edx, 2Ah ; '*'
0x1800269bb  call    WPP_SF_
0x1800269c0  lea     rcx, [rbx+10h]; lpCriticalSection
0x1800269c4  call    cs:__imp_EnterCriticalSection
0x1800269ca  mov     r8d, edi
0x1800269cd  mov     rdx, rsi
0x1800269d0  mov     ecx, 1
0x1800269d5  call    ?GetSymLinkFromCmEventData@ApfHelper@Apx@@SAPEBGW4_CM_NOTIFY_ACTION@@PEAU_CM_NOTIFY_EVENT_DATA@@K@Z; Apx::ApfHelper::GetSymLinkFromCmEventData(_CM_NOTIFY_ACTION,_CM_NOTIFY_EVENT_DATA *,ulong)
0x1800269da  xor     esi, esi
0x1800269dc  mov     r10, rax
0x1800269df  test    rax, rax
0x1800269e2  jnz     short loc_180026A1F
0x1800269e4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800269eb  cmp     rcx, r14
0x1800269ee  jz      loc_180026AF5
0x1800269f4  test    byte ptr [rcx+1Ch], 80h
0x1800269f8  jz      loc_180026AF5
0x1800269fe  cmp     byte ptr [rcx+19h], 2
0x180026a02  jb      loc_180026AF5
0x180026a08  mov     rcx, [rcx+10h]
0x180026a0c  lea     edx, [rax+2Bh]
0x180026a0f  mov     r9, rbx
0x180026a12  not     r9
0x180026a15  call    WPP_SF_q
0x180026a1a  jmp     loc_180026AF5
0x180026a1f  lea     rdi, [rbx+76h]
0x180026a23  mov     r8, r10
0x180026a26  mov     rax, rdi
0x180026a29  sub     r8, rdi
0x180026a2c  movzx   ecx, word ptr [rax]
0x180026a2f  movzx   edx, word ptr [rax+r8]
0x180026a34  sub     ecx, edx
0x180026a36  jnz     short loc_180026A40
0x180026a38  add     rax, 2
0x180026a3c  test    edx, edx
0x180026a3e  jnz     short loc_180026A2C
0x180026a40  test    ecx, ecx
0x180026a42  jz      short loc_180026A83
0x180026a44  mov     rcx, cs:WPP_GLOBAL_Control
0x180026a4b  cmp     rcx, r14
0x180026a4e  jz      loc_180026AF5
0x180026a54  test    byte ptr [rcx+1Ch], 80h
0x180026a58  jz      loc_180026AF5
0x180026a5e  cmp     byte ptr [rcx+19h], 4
0x180026a62  jb      loc_180026AF5
0x180026a68  mov     rcx, [rcx+10h]; LoggerHandle
0x180026a6c  mov     r9, rbx
0x180026a6f  mov     [rsp+58h+var_30], r10; __int64
0x180026a74  not     r9
0x180026a77  mov     [rsp+58h+var_38], rdi; __int64
0x180026a7c  call    WPP_SF_qSS
0x180026a81  jmp     short loc_180026AF5
0x180026a83  mov     rcx, cs:WPP_GLOBAL_Control
0x180026a8a  cmp     rcx, r14
0x180026a8d  jz      short loc_180026AAF
0x180026a8f  test    byte ptr [rcx+1Ch], 80h
0x180026a93  jz      short loc_180026AAF
0x180026a95  cmp     byte ptr [rcx+19h], 4
0x180026a99  jb      short loc_180026AAF
0x180026a9b  mov     rcx, [rcx+10h]
0x180026a9f  mov     r9, rbx
0x180026aa2  not     r9
0x180026aa5  mov     edx, 2Dh ; '-'
0x180026aaa  call    WPP_SF_q
0x180026aaf  xor     edx, edx; Val
0x180026ab1  mov     r8d, 20Ah; Size
0x180026ab7  mov     rcx, rdi; void *
0x180026aba  call    memset_0
0x180026abf  mov     rcx, [rbx+58h]; hFile
0x180026ac3  test    rcx, rcx
0x180026ac6  jz      short loc_180026AF5
0x180026ac8  xor     edx, edx; lpOverlapped
0x180026aca  call    cs:__imp_CancelIoEx
0x180026ad0  mov     rcx, [rbx+58h]; hObject
0x180026ad4  test    rcx, rcx
0x180026ad7  jz      short loc_180026AE3
0x180026ad9  call    cs:__imp_CloseHandle
0x180026adf  mov     [rbx+58h], rsi
0x180026ae3  mov     rcx, [rbx+40h]
0x180026ae7  mov     r8b, 1
0x180026aea  mov     rax, [rbx+38h]
0x180026aee  xor     edx, edx
0x180026af0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026af5  lea     rcx, [rbx+10h]; lpCriticalSection
0x180026af9  call    cs:__imp_LeaveCriticalSection
0x180026aff  mov     rcx, [rbx+68h]
0x180026b03  test    rcx, rcx
0x180026b06  jz      short loc_180026B12
0x180026b08  call    cs:__imp_CM_Unregister_Notification
0x180026b0e  mov     [rbx+68h], rsi
0x180026b12  mov     [rbx+75h], sil
0x180026b16  mov     rcx, cs:WPP_GLOBAL_Control
0x180026b1d  cmp     rcx, r14
0x180026b20  jz      short loc_180026B43
0x180026b22  test    byte ptr [rcx+1Ch], 1
0x180026b26  jz      short loc_180026B43
0x180026b28  cmp     byte ptr [rcx+19h], 5
0x180026b2c  jb      short loc_180026B43
0x180026b2e  mov     rcx, [rcx+10h]
0x180026b32  lea     r8, WPP_e6720f2ec66938db1e8abec7a65481bb_Traceguids
0x180026b39  mov     edx, 2Eh ; '.'
0x180026b3e  call    WPP_SF_
0x180026b43  add     rsp, 30h
0x180026b47  pop     r14
0x180026b49  pop     rdi
0x180026b4a  pop     rsi
0x180026b4b  pop     rbp
0x180026b4c  pop     rbx
0x180026b4d  retn
```
