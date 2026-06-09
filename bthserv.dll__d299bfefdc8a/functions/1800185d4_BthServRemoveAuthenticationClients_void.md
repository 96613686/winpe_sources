# BthServRemoveAuthenticationClients(void *)

- ea: `0x1800185d4`
- end: `0x1800187cc`
- name: `?BthServRemoveAuthenticationClients@@YAXPEAX@Z`
- size: `504`
- prototype: `void __fastcall(char *)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180011dec`

## callees

- `0x1800110d0`
- `0x1800110fc`
- `0x18001140c`
- `0x180017848`
- `0x18001815c`
- `0x1800185d4`

## import_xrefs

- `ntdll!RtlRbRemoveNode` at `0x180018730`
- `ntdll!RtlRbRemoveNode` at `0x180018730`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180018761`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180018761`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180018657`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180018657`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall BthServRemoveAuthenticationClients(char *a1)
{
  char v2; // di
  bool v3; // dl
  _QWORD **v4; // rsi
  _QWORD *v5; // rax
  _QWORD *v6; // rcx
  _QWORD *v7; // r14
  __int64 v8; // rcx
  __int64 v9; // rdx
  _QWORD *v10; // rax
  _QWORD *v11; // r15
  unsigned __int64 v12; // rbx
  int v13; // ebp
  int v14; // eax
  unsigned __int64 v15; // rax
  int v16; // r8d

  v2 = 1;
  v3 = WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u;
  if ( v3 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_AND_TRACE_SF_si(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v3,
      WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED,
      *((_QWORD *)WPP_GLOBAL_Control + 5));
  if ( !WaitForSingleObject(hMutex, 0xFFFFFFFF) )
  {
    v4 = (_QWORD **)(a1 + 16);
    while ( 1 )
    {
      v5 = *v4;
      if ( *v4 == v4 )
      {
        ReleaseMutex(hMutex);
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u )
          v2 = 0;
        if ( v2 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          LOBYTE(v16) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
          WPP_RECORDER_AND_TRACE_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), v2, v16, *((_QWORD *)WPP_GLOBAL_Control + 5));
        }
        return;
      }
      if ( (_QWORD **)v5[1] != v4
        || (v6 = (_QWORD *)*v5, *(_QWORD **)(*v5 + 8LL) != v5)
        || (*v4 = v6,
            v7 = v5 - 4,
            v6[1] = v4,
            v8 = (__int64)(v5 - 2),
            v9 = *(_QWORD *)v8,
            *(_QWORD *)(*(_QWORD *)v8 + 8LL) != v8)
        || (v10 = (_QWORD *)v7[3], *v10 != v8) )
      {
        __fastfail(3u);
      }
      *v10 = v9;
      *(_QWORD *)(v9 + 8) = v10;
      v11 = (_QWORD *)v7[1];
      if ( (_QWORD *)v11[5] == v11 + 5 )
      {
        v12 = (unsigned __int64)qword_180044B38;
        if ( (qword_180044B40 & 1) != 0 )
        {
          if ( !qword_180044B38 )
            goto LABEL_31;
          v12 = (unsigned __int64)&qword_180044B38 ^ (unsigned __int64)qword_180044B38;
        }
        v13 = qword_180044B40 & 1;
        if ( v12 )
        {
          do
          {
            v14 = BthServAuthenticationClientCompare(v11, (struct _RTL_BALANCED_NODE *)v12);
            if ( v14 >= 0 )
            {
              if ( v14 <= 0 )
                break;
              v15 = *(_QWORD *)(v12 + 8);
            }
            else
            {
              v15 = *(_QWORD *)v12;
            }
            if ( v13 && v15 )
              v12 ^= v15;
            else
              v12 = v15;
          }
          while ( v12 );
          if ( v12 )
          {
            RtlRbRemoveNode(&qword_180044B38, v12);
            SdpFreePool(v12);
          }
        }
      }
LABEL_31:
      BthServReleaseClientResources(v7);
      SdpFreePool(v7);
    }
  }
}

```

## disassembly

```asm
0x1800185d4  push    rbx
0x1800185d6  push    rbp
0x1800185d7  push    rsi
0x1800185d8  push    rdi
0x1800185d9  push    r12
0x1800185db  push    r13
0x1800185dd  push    r14
0x1800185df  push    r15
0x1800185e1  sub     rsp, 58h
0x1800185e5  mov     rbx, rcx
0x1800185e8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800185ef  lea     r12, WPP_GLOBAL_Control
0x1800185f6  mov     edi, 1
0x1800185fb  cmp     rcx, r12
0x1800185fe  jz      short loc_18001860B
0x180018600  cmp     byte ptr [rcx+19h], 4
0x180018604  jb      short loc_18001860B
0x180018606  mov     dl, dil
0x180018609  jmp     short loc_18001860D
0x18001860b  xor     dl, dl
0x18001860d  lea     rbp, WPP_RECORDER_INITIALIZED
0x180018614  cmp     cs:WPP_RECORDER_INITIALIZED, rbp
0x18001861b  lea     rbp, WPP_8f95a5b1d9133c17f605a10539329b05_Traceguids
0x180018622  setnz   r8b
0x180018626  test    dl, dl
0x180018628  jnz     short loc_18001862F
0x18001862a  test    r8b, r8b
0x18001862d  jz      short loc_18001864D
0x18001862f  mov     r9, [rcx+28h]
0x180018633  mov     rcx, [rcx+10h]
0x180018637  mov     [rsp+98h+var_50], rbx
0x18001863c  mov     [rsp+98h+var_60], rbp
0x180018641  mov     [rsp+98h+var_68], 19h
0x180018648  call    WPP_RECORDER_AND_TRACE_SF_si
0x18001864d  mov     rcx, cs:hMutex; hHandle
0x180018654  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180018657  call    cs:__imp_WaitForSingleObject
0x18001865d  test    eax, eax
0x18001865f  jnz     loc_1800187BB
0x180018665  lea     rsi, [rbx+10h]
0x180018669  lea     r13, qword_180044B38
0x180018670  mov     rax, [rsi]
0x180018673  cmp     rax, rsi
0x180018676  jz      loc_18001875A
0x18001867c  cmp     [rax+8], rsi
0x180018680  jnz     loc_180018753
0x180018686  mov     rcx, [rax]
0x180018689  cmp     [rcx+8], rax
0x18001868d  jnz     loc_180018753
0x180018693  mov     [rsi], rcx
0x180018696  lea     r14, [rax-20h]
0x18001869a  mov     [rcx+8], rsi
0x18001869e  lea     rcx, [r14+10h]
0x1800186a2  mov     rdx, [rcx]
0x1800186a5  cmp     [rdx+8], rcx
0x1800186a9  jnz     loc_180018753
0x1800186af  mov     rax, [r14+18h]
0x1800186b3  cmp     [rax], rcx
0x1800186b6  jnz     loc_180018753
0x1800186bc  mov     [rax], rdx
0x1800186bf  mov     [rdx+8], rax
0x1800186c3  mov     r15, [r14+8]
0x1800186c7  lea     rax, [r15+28h]
0x1800186cb  cmp     [rax], rax
0x1800186ce  jnz     short loc_18001873E
0x1800186d0  mov     rax, cs:qword_180044B40
0x1800186d7  mov     rbx, cs:qword_180044B38
0x1800186de  test    dil, al
0x1800186e1  jz      short loc_1800186EB
0x1800186e3  test    rbx, rbx
0x1800186e6  jz      short loc_18001873E
0x1800186e8  xor     rbx, r13
0x1800186eb  movzx   ebp, al
0x1800186ee  and     ebp, edi
0x1800186f0  test    rbx, rbx
0x1800186f3  jz      short loc_18001873E
0x1800186f5  mov     rdx, rbx; struct _RTL_BALANCED_NODE *
0x1800186f8  mov     rcx, r15; void *
0x1800186fb  call    ?BthServAuthenticationClientCompare@@YAJPEAXPEAU_RTL_BALANCED_NODE@@@Z; BthServAuthenticationClientCompare(void *,_RTL_BALANCED_NODE *)
0x180018700  test    eax, eax
0x180018702  jns     short loc_180018709
0x180018704  mov     rax, [rbx]
0x180018707  jmp     short loc_18001870F
0x180018709  jle     short loc_180018725
0x18001870b  mov     rax, [rbx+8]
0x18001870f  test    ebp, ebp
0x180018711  jz      short loc_18001871D
0x180018713  test    rax, rax
0x180018716  jz      short loc_18001871D
0x180018718  xor     rbx, rax
0x18001871b  jmp     short loc_180018720
0x18001871d  mov     rbx, rax
0x180018720  test    rbx, rbx
0x180018723  jnz     short loc_1800186F5
0x180018725  test    rbx, rbx
0x180018728  jz      short loc_18001873E
0x18001872a  mov     rdx, rbx
0x18001872d  mov     rcx, r13
0x180018730  call    cs:__imp_RtlRbRemoveNode
0x180018736  mov     rcx, rbx
0x180018739  call    SdpFreePool
0x18001873e  mov     rcx, r14
0x180018741  call    BthServReleaseClientResources
0x180018746  mov     rcx, r14
0x180018749  call    SdpFreePool
0x18001874e  jmp     loc_180018670
0x180018753  mov     ecx, 3
0x180018758  int     29h; Win8: RtlFailFast(ecx)
0x18001875a  mov     rcx, cs:hMutex; hMutex
0x180018761  call    cs:__imp_ReleaseMutex
0x180018767  mov     rcx, cs:WPP_GLOBAL_Control
0x18001876e  cmp     rcx, r12
0x180018771  jz      short loc_180018779
0x180018773  cmp     byte ptr [rcx+19h], 4
0x180018777  jnb     short loc_18001877C
0x180018779  xor     dil, dil
0x18001877c  lea     rax, WPP_RECORDER_INITIALIZED
0x180018783  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x18001878a  setnz   r8b
0x18001878e  test    dil, dil
0x180018791  jnz     short loc_180018798
0x180018793  test    r8b, r8b
0x180018796  jz      short loc_1800187BB
0x180018798  mov     r9, [rcx+28h]
0x18001879c  lea     rdx, WPP_8f95a5b1d9133c17f605a10539329b05_Traceguids
0x1800187a3  mov     rcx, [rcx+10h]
0x1800187a7  mov     [rsp+98h+var_60], rdx
0x1800187ac  mov     dl, dil
0x1800187af  mov     [rsp+98h+var_68], 1Ah
0x1800187b6  call    WPP_RECORDER_AND_TRACE_SF_s
0x1800187bb  add     rsp, 58h
0x1800187bf  pop     r15
0x1800187c1  pop     r14
0x1800187c3  pop     r13
0x1800187c5  pop     r12
0x1800187c7  pop     rdi
0x1800187c8  pop     rsi
0x1800187c9  pop     rbp
0x1800187ca  pop     rbx
0x1800187cb  retn
```
