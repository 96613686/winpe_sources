# BthServRemoveAuthenticationClientByEventHandle(void *,unsigned __int64 *,unsigned __int64)

- ea: `0x180018224`
- end: `0x1800185cc`
- name: `?BthServRemoveAuthenticationClientByEventHandle@@YAJPEAXPEA_K_K@Z`
- size: `936`
- prototype: `__int64 __fastcall(_QWORD *, unsigned __int64 *, __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800120f0`

## callees

- `0x1800110d0`
- `0x180011194`
- `0x180012e00`
- `0x180017848`
- `0x18001815c`
- `0x180018224`
- `0x1800190ac`

## import_xrefs

- `ntdll!RtlRbRemoveNode` at `0x1800183e9`
- `ntdll!RtlRbRemoveNode` at `0x1800183e9`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800183fe`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180018475`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18001854d`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800183fe`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180018475`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18001854d`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800182bf`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800182bf`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall BthServRemoveAuthenticationClientByEventHandle(_QWORD *a1, unsigned __int64 *a2, __int64 a3)
{
  __int64 v3; // r14
  char v5; // di
  bool v6; // dl
  int v7; // edx
  int v8; // r8d
  unsigned __int64 v9; // rbx
  _QWORD *v10; // rsi
  struct _OVERLAPPED *v11; // rbp
  void *InternalHigh; // r12
  int v13; // r14d
  int v14; // eax
  unsigned __int64 v15; // rax
  _QWORD *v16; // rcx
  struct _OVERLAPPED **Pointer; // rdx
  struct _OVERLAPPED **hEvent; // r8
  __int64 v19; // rdx
  _QWORD *v20; // rax
  int v21; // r8d
  __int64 *v22; // rdx
  int v24; // r8d
  _QWORD *v25; // rcx
  __int64 *v26; // rdx
  int v27; // [rsp+20h] [rbp-88h]
  int v28; // [rsp+28h] [rbp-80h]
  int v29; // [rsp+30h] [rbp-78h]
  __int16 v30; // [rsp+30h] [rbp-78h]
  int v31; // [rsp+38h] [rbp-70h]
  __int64 v32; // [rsp+C0h] [rbp+18h]

  v32 = a3;
  v3 = a3;
  v5 = 1;
  v6 = WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u;
  if ( v6 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(a3) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    WPP_RECORDER_AND_TRACE_SF_sqi(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v6,
      a3,
      *((_QWORD *)WPP_GLOBAL_Control + 5),
      v27,
      v28,
      20,
      (__int64)WPP_8f95a5b1d9133c17f605a10539329b05_Traceguids);
  }
  if ( WaitForSingleObject(hMutex, 0xFFFFFFFF) )
    return 2147942567LL;
  v9 = 0;
  v10 = (_QWORD *)a1[2];
  if ( v10 != a1 + 2 )
  {
    while ( 1 )
    {
      v11 = (struct _OVERLAPPED *)(v10 - 4);
      if ( v10[4] == v3 )
      {
        v9 = (unsigned __int64)qword_180044B38;
        if ( (qword_180044B40 & 1) != 0 )
        {
          if ( !qword_180044B38 )
            goto LABEL_41;
          v9 = (unsigned __int64)&qword_180044B38 ^ (unsigned __int64)qword_180044B38;
        }
        InternalHigh = (void *)v11->InternalHigh;
        v13 = qword_180044B40 & 1;
        if ( !v9 )
          goto LABEL_41;
        do
        {
          v14 = BthServAuthenticationClientCompare(InternalHigh, (struct _RTL_BALANCED_NODE *)v9);
          if ( v14 >= 0 )
          {
            if ( v14 <= 0 )
              break;
            v15 = *(_QWORD *)(v9 + 8);
          }
          else
          {
            v15 = *(_QWORD *)v9;
          }
          if ( v13 && v15 )
            v9 ^= v15;
          else
            v9 = v15;
        }
        while ( v9 );
        if ( !v9 )
        {
LABEL_41:
          ReleaseMutex(hMutex);
          v25 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u )
            v5 = 0;
          LOBYTE(v24) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
          if ( v5 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          {
            v26 = WPP_8f95a5b1d9133c17f605a10539329b05_Traceguids;
            v30 = 21;
            goto LABEL_61;
          }
          return 2147943568LL;
        }
        v3 = v32;
      }
      v16 = v10;
      v10 = (_QWORD *)*v10;
      if ( v10 == a1 + 2 )
      {
        if ( !v9 )
          break;
        Pointer = (struct _OVERLAPPED **)v11->Pointer;
        if ( Pointer[1] != (struct _OVERLAPPED *)&v11->Offset
          || (hEvent = (struct _OVERLAPPED **)v11->hEvent, *hEvent != (struct _OVERLAPPED *)&v11->Offset)
          || (*hEvent = (struct _OVERLAPPED *)Pointer,
              Pointer[1] = (struct _OVERLAPPED *)hEvent,
              v19 = *v16,
              *(_QWORD **)(*v16 + 8LL) != v16)
          || (v20 = (_QWORD *)v16[1], (_QWORD *)*v20 != v16) )
        {
          __fastfail(3u);
        }
        *v20 = v19;
        *(_QWORD *)(v19 + 8) = v20;
        BthServReleaseClientResources(v11);
        SdpFreePool(v11);
        if ( *(_QWORD *)(v9 + 40) == v9 + 40 )
        {
          RtlRbRemoveNode(&qword_180044B38, v9);
          SdpFreePool(v9);
        }
        ReleaseMutex(hMutex);
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u )
          v5 = 0;
        if ( v5 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          v22 = WPP_8f95a5b1d9133c17f605a10539329b05_Traceguids;
          LOBYTE(v22) = v5;
          LOBYTE(v21) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
          WPP_RECORDER_AND_TRACE_SF_sd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            (_DWORD)v22,
            v21,
            *((_QWORD *)WPP_GLOBAL_Control + 5),
            v27,
            v28,
            24,
            (__int64)WPP_8f95a5b1d9133c17f605a10539329b05_Traceguids);
        }
        return 0;
      }
    }
  }
  LOBYTE(v7) = WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u;
  if ( (_BYTE)v7 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v8) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    WPP_RECORDER_AND_TRACE_SF_sqqiq(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v7,
      v8,
      *((_QWORD *)WPP_GLOBAL_Control + 5),
      v27,
      v28,
      v29,
      v31);
  }
  ReleaseMutex(hMutex);
  v25 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u )
    v5 = 0;
  LOBYTE(v24) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
  if ( v5 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    v26 = WPP_8f95a5b1d9133c17f605a10539329b05_Traceguids;
    v30 = 23;
LABEL_61:
    LOBYTE(v26) = v5;
    WPP_RECORDER_AND_TRACE_SF_sd(
      v25[2],
      (_DWORD)v26,
      v24,
      v25[5],
      v27,
      v28,
      v30,
      (__int64)WPP_8f95a5b1d9133c17f605a10539329b05_Traceguids);
  }
  return 2147943568LL;
}

```

## disassembly

```asm
0x180018224  mov     [rsp+arg_0], rbx
0x180018229  mov     [rsp+arg_10], r8
0x18001822e  mov     [rsp+arg_8], rdx
0x180018233  push    rbp
0x180018234  push    rsi
0x180018235  push    rdi
0x180018236  push    r12
0x180018238  push    r13
0x18001823a  push    r14
0x18001823c  push    r15
0x18001823e  sub     rsp, 70h
0x180018242  mov     r14, r8
0x180018245  mov     rbp, rdx
0x180018248  mov     r13, rcx
0x18001824b  mov     rcx, cs:WPP_GLOBAL_Control
0x180018252  lea     rax, WPP_GLOBAL_Control
0x180018259  mov     edi, 1
0x18001825e  cmp     rcx, rax
0x180018261  jz      short loc_18001826E
0x180018263  cmp     byte ptr [rcx+19h], 4
0x180018267  jb      short loc_18001826E
0x180018269  mov     dl, dil
0x18001826c  jmp     short loc_180018270
0x18001826e  xor     dl, dl
0x180018270  lea     r12, WPP_RECORDER_INITIALIZED
0x180018277  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x18001827e  lea     r9, WPP_8f95a5b1d9133c17f605a10539329b05_Traceguids
0x180018285  setnz   r8b
0x180018289  test    dl, dl
0x18001828b  jnz     short loc_180018292
0x18001828d  test    r8b, r8b
0x180018290  jz      short loc_1800182B5
0x180018292  mov     [rsp+0A8h+var_58], r14
0x180018297  mov     [rsp+0A8h+var_60], r13
0x18001829c  mov     qword ptr [rsp+0A8h+var_70], r9
0x1800182a1  mov     r9, [rcx+28h]
0x1800182a5  mov     rcx, [rcx+10h]
0x1800182a9  mov     [rsp+0A8h+var_78], 14h
0x1800182b0  call    WPP_RECORDER_AND_TRACE_SF_sqi
0x1800182b5  mov     rcx, cs:hMutex; hHandle
0x1800182bc  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1800182bf  call    cs:__imp_WaitForSingleObject
0x1800182c5  test    eax, eax
0x1800182c7  jnz     loc_1800185AF
0x1800182cd  lea     r15, [r13+10h]
0x1800182d1  xor     ebx, ebx
0x1800182d3  mov     rsi, [r15]
0x1800182d6  cmp     rsi, r15
0x1800182d9  jz      loc_1800184ED
0x1800182df  lea     r12, qword_180044B38
0x1800182e6  lea     rbp, [rsi-20h]
0x1800182ea  cmp     [rbp+40h], r14
0x1800182ee  jnz     short loc_18001836C
0x1800182f0  mov     rax, cs:qword_180044B40
0x1800182f7  mov     rbx, cs:qword_180044B38
0x1800182fe  test    dil, al
0x180018301  jz      short loc_18001830F
0x180018303  test    rbx, rbx
0x180018306  jz      loc_18001846E
0x18001830c  xor     rbx, r12
0x18001830f  mov     r12, [rbp+8]
0x180018313  movzx   r14d, al
0x180018317  and     r14d, edi
0x18001831a  test    rbx, rbx
0x18001831d  jz      loc_18001846E
0x180018323  mov     rdx, rbx; struct _RTL_BALANCED_NODE *
0x180018326  mov     rcx, r12; void *
0x180018329  call    ?BthServAuthenticationClientCompare@@YAJPEAXPEAU_RTL_BALANCED_NODE@@@Z; BthServAuthenticationClientCompare(void *,_RTL_BALANCED_NODE *)
0x18001832e  test    eax, eax
0x180018330  jns     short loc_180018337
0x180018332  mov     rax, [rbx]
0x180018335  jmp     short loc_18001833D
0x180018337  jle     short loc_180018354
0x180018339  mov     rax, [rbx+8]
0x18001833d  test    r14d, r14d
0x180018340  jz      short loc_18001834C
0x180018342  test    rax, rax
0x180018345  jz      short loc_18001834C
0x180018347  xor     rbx, rax
0x18001834a  jmp     short loc_18001834F
0x18001834c  mov     rbx, rax
0x18001834f  test    rbx, rbx
0x180018352  jnz     short loc_180018323
0x180018354  test    rbx, rbx
0x180018357  jz      loc_18001846E
0x18001835d  mov     r14, [rsp+0A8h+arg_10]
0x180018365  lea     r12, qword_180044B38
0x18001836c  mov     rcx, rsi
0x18001836f  mov     rsi, [rsi]
0x180018372  cmp     rsi, r15
0x180018375  jnz     loc_1800182E6
0x18001837b  test    rbx, rbx
0x18001837e  jz      loc_1800184DE
0x180018384  lea     rax, [rbp+10h]
0x180018388  mov     rdx, [rax]
0x18001838b  cmp     [rdx+8], rax
0x18001838f  jnz     loc_1800184D7
0x180018395  mov     r8, [rax+8]
0x180018399  cmp     [r8], rax
0x18001839c  jnz     loc_1800184D7
0x1800183a2  mov     [r8], rdx
0x1800183a5  mov     [rdx+8], r8
0x1800183a9  mov     rdx, [rcx]
0x1800183ac  cmp     [rdx+8], rcx
0x1800183b0  jnz     loc_1800184D7
0x1800183b6  mov     rax, [rcx+8]
0x1800183ba  cmp     [rax], rcx
0x1800183bd  jnz     loc_1800184D7
0x1800183c3  mov     [rax], rdx
0x1800183c6  mov     rcx, rbp
0x1800183c9  mov     [rdx+8], rax
0x1800183cd  call    BthServReleaseClientResources
0x1800183d2  mov     rcx, rbp
0x1800183d5  call    SdpFreePool
0x1800183da  lea     rax, [rbx+28h]
0x1800183de  cmp     [rax], rax
0x1800183e1  jnz     short loc_1800183F7
0x1800183e3  mov     rdx, rbx
0x1800183e6  mov     rcx, r12
0x1800183e9  call    cs:__imp_RtlRbRemoveNode
0x1800183ef  mov     rcx, rbx
0x1800183f2  call    SdpFreePool
0x1800183f7  mov     rcx, cs:hMutex; hMutex
0x1800183fe  call    cs:__imp_ReleaseMutex
0x180018404  mov     rcx, cs:WPP_GLOBAL_Control
0x18001840b  lea     rbx, WPP_GLOBAL_Control
0x180018412  cmp     rcx, rbx
0x180018415  jz      short loc_18001841D
0x180018417  cmp     byte ptr [rcx+19h], 4
0x18001841b  jnb     short loc_180018420
0x18001841d  xor     dil, dil
0x180018420  lea     rax, WPP_RECORDER_INITIALIZED
0x180018427  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x18001842e  setnz   r8b
0x180018432  test    dil, dil
0x180018435  jnz     short loc_18001843C
0x180018437  test    r8b, r8b
0x18001843a  jz      short loc_180018467
0x18001843c  mov     r9, [rcx+28h]
0x180018440  lea     rdx, WPP_8f95a5b1d9133c17f605a10539329b05_Traceguids
0x180018447  mov     rcx, [rcx+10h]
0x18001844b  mov     dword ptr [rsp+0A8h+var_60], 0
0x180018453  mov     qword ptr [rsp+0A8h+var_70], rdx
0x180018458  mov     dl, dil
0x18001845b  mov     [rsp+0A8h+var_78], 18h
0x180018462  call    WPP_RECORDER_AND_TRACE_SF_sd
0x180018467  xor     eax, eax
0x180018469  jmp     loc_1800185B4
0x18001846e  mov     rcx, cs:hMutex; hMutex
0x180018475  call    cs:__imp_ReleaseMutex
0x18001847b  mov     rcx, cs:WPP_GLOBAL_Control
0x180018482  lea     rbx, WPP_GLOBAL_Control
0x180018489  cmp     rcx, rbx
0x18001848c  jz      short loc_180018494
0x18001848e  cmp     byte ptr [rcx+19h], 4
0x180018492  jnb     short loc_180018497
0x180018494  xor     dil, dil
0x180018497  lea     rax, WPP_RECORDER_INITIALIZED
0x18001849e  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1800184a5  setnz   r8b
0x1800184a9  test    dil, dil
0x1800184ac  jnz     short loc_1800184B7
0x1800184ae  test    r8b, r8b
0x1800184b1  jz      loc_1800185A8
0x1800184b7  mov     dword ptr [rsp+0A8h+var_60], 490h
0x1800184bf  lea     rdx, WPP_8f95a5b1d9133c17f605a10539329b05_Traceguids
0x1800184c6  mov     qword ptr [rsp+0A8h+var_70], rdx
0x1800184cb  mov     [rsp+0A8h+var_78], 15h
0x1800184d2  jmp     loc_180018598
0x1800184d7  mov     ecx, 3
0x1800184dc  int     29h; Win8: RtlFailFast(ecx)
0x1800184de  mov     rbp, [rsp+0A8h+arg_8]
0x1800184e6  lea     r12, WPP_RECORDER_INITIALIZED
0x1800184ed  mov     rcx, cs:WPP_GLOBAL_Control
0x1800184f4  lea     rbx, WPP_GLOBAL_Control
0x1800184fb  cmp     rcx, rbx
0x1800184fe  jz      short loc_18001850B
0x180018500  cmp     byte ptr [rcx+19h], 3
0x180018504  jb      short loc_18001850B
0x180018506  mov     dl, dil
0x180018509  jmp     short loc_18001850D
0x18001850b  xor     dl, dl
0x18001850d  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x180018514  setnz   r8b
0x180018518  test    dl, dl
0x18001851a  jnz     short loc_180018521
0x18001851c  test    r8b, r8b
0x18001851f  jz      short loc_180018546
0x180018521  mov     rax, [rbp+0]
0x180018525  mov     r9, [rcx+28h]
0x180018529  mov     rcx, [rcx+10h]
0x18001852d  mov     [rsp+0A8h+var_48], r14
0x180018532  mov     [rsp+0A8h+var_50], rax
0x180018537  mov     [rsp+0A8h+var_58], rbp
0x18001853c  mov     [rsp+0A8h+var_60], r13
0x180018541  call    WPP_RECORDER_AND_TRACE_SF_sqqiq
0x180018546  mov     rcx, cs:hMutex; hMutex
0x18001854d  call    cs:__imp_ReleaseMutex
0x180018553  mov     rcx, cs:WPP_GLOBAL_Control
0x18001855a  cmp     rcx, rbx
0x18001855d  jz      short loc_180018565
0x18001855f  cmp     byte ptr [rcx+19h], 4
0x180018563  jnb     short loc_180018568
0x180018565  xor     dil, dil
0x180018568  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x18001856f  setnz   r8b
0x180018573  test    dil, dil
0x180018576  jnz     short loc_18001857D
0x180018578  test    r8b, r8b
0x18001857b  jz      short loc_1800185A8
0x18001857d  mov     dword ptr [rsp+0A8h+var_60], 490h
0x180018585  lea     rdx, WPP_8f95a5b1d9133c17f605a10539329b05_Traceguids
0x18001858c  mov     qword ptr [rsp+0A8h+var_70], rdx
0x180018591  mov     [rsp+0A8h+var_78], 17h
0x180018598  mov     r9, [rcx+28h]
0x18001859c  mov     dl, dil
0x18001859f  mov     rcx, [rcx+10h]
0x1800185a3  call    WPP_RECORDER_AND_TRACE_SF_sd
0x1800185a8  mov     eax, 80070490h
0x1800185ad  jmp     short loc_1800185B4
0x1800185af  mov     eax, 800700A7h
0x1800185b4  mov     rbx, [rsp+0A8h+arg_0]
0x1800185bc  add     rsp, 70h
0x1800185c0  pop     r15
0x1800185c2  pop     r14
0x1800185c4  pop     r13
0x1800185c6  pop     r12
0x1800185c8  pop     rdi
0x1800185c9  pop     rsi
0x1800185ca  pop     rbp
0x1800185cb  retn
```
