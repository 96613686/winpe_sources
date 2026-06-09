# PeriodicUpdateManager::UnpackPersistedEvent(_GUID,void *,_PERSISTED_PERIODIC_UPDATE * *,int *)

- ea: `0x180032ed4`
- end: `0x1800330e7`
- name: `?UnpackPersistedEvent@PeriodicUpdateManager@@CAJU_GUID@@PEAXPEAPEAU_PERSISTED_PERIODIC_UPDATE@@PEAH@Z`
- size: `531`
- prototype: `static int(struct _GUID *__struct_ptr, void *, struct _PERSISTED_PERIODIC_UPDATE **, int *)`
- caller_count: `4`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180032980`
- `0x180032b54`
- `0x18008e370`
- `0x1800a7538`

## callees

- `0x18002ee38`
- `0x180032ed4`
- `0x1800af0a4`
- `0x1800bc541`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180032f97`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180032f97`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180032f89`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180032f89`
- `ntdll!RtlNtStatusToDosError` at `0x180032fcf`
- `ntdll!RtlNtStatusToDosError` at `0x180032fcf`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x180033048`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x180033048`
- `api-ms-win-core-biptcltapi-l1-1-7!BiPtQueryBrokeredEvent` at `0x180032f0f`
- `api-ms-win-core-biptcltapi-l1-1-7!BiPtQueryBrokeredEvent` at `0x180032f0f`
- `api-ms-win-core-biptcltapi-l1-1-7!BiPtFreeMemory` at `0x180032f5d`
- `api-ms-win-core-biptcltapi-l1-1-7!BiPtFreeMemory` at `0x180032f5d`
- `api-ms-win-core-biptcltapi-l1-1-7!BiPtDeleteEvent` at `0x180032ff0`
- `api-ms-win-core-biptcltapi-l1-1-7!BiPtDeleteEvent` at `0x180032ff0`

## string_xrefs

- `0x180032f28`: `onecoreuap\base\diagnosis\platform\notifications\platform\endpoint\periodicupdatemanager.cpp`
- `0x180032ffb`: `onecoreuap\base\diagnosis\platform\notifications\platform\endpoint\periodicupdatemanager.cpp`
- `0x1800330ab`: `onecoreuap\base\diagnosis\platform\notifications\platform\endpoint\periodicupdatemanager.cpp`

## pseudocode

```c
__int64 __fastcall PeriodicUpdateManager::UnpackPersistedEvent(
        struct _GUID *a1,
        void *a2,
        struct _PERSISTED_PERIODIC_UPDATE **a3,
        int *a4)
{
  NTSTATUS v8; // eax
  unsigned int v9; // ebx
  _QWORD *v10; // rcx
  char *v12; // rsi
  HANDLE ProcessHeap; // rax
  void *v14; // rbx
  signed int v15; // eax
  __int64 v16; // rdx
  __int64 v17; // r9
  size_t Size; // [rsp+20h] [rbp-38h] BYREF
  unsigned int *v19; // [rsp+28h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  v19 = 0;
  LODWORD(Size) = 0;
  if ( a4 )
    *a4 = 1;
  v8 = BiPtQueryBrokeredEvent(a1, &Size, &v19);
  if ( v8 < 0 )
  {
    v15 = RtlNtStatusToDosError(v8);
    v9 = v15;
    if ( v15 > 0 )
      v9 = (unsigned __int16)v15 | 0x80070000;
  }
  else
  {
    v9 = 0;
  }
  if ( (v9 & 0x80000000) == 0 )
  {
    if ( v19[12] == 4772 )
    {
      v12 = (char *)v19 + v19[10];
      LODWORD(Size) = 4772;
      ProcessHeap = GetProcessHeap();
      v14 = HeapAlloc(ProcessHeap, 0, 0x12A4u);
      if ( v14 )
      {
        memcpy_0(v14, (char *)v19 + v19[11], (unsigned int)Size);
        if ( a2 && !EqualSid(a2, v12) && a4 )
          *a4 = 0;
        *a3 = (struct _PERSISTED_PERIODIC_UPDATE *)v14;
        v9 = 0;
      }
      else
      {
        v9 = -2147024882;
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x8D,
          (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\periodicupdatemanager.cpp",
          (const char *)0x8007000ELL,
          Size);
        v10 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
        {
          v16 = 12;
          v17 = 2147942414LL;
          goto LABEL_24;
        }
      }
    }
    else
    {
      BiPtDeleteEvent(a1);
      v9 = -2147024809;
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x86,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\periodicupdatemanager.cpp",
        (const char *)0x80070057LL,
        Size);
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
      {
        v16 = 11;
        v17 = 2147942487LL;
LABEL_24:
        WPP_SF_d(v10[2], v16, WPP_6b3164ff505c38b9d951495712a9c50a_Traceguids, v17);
      }
    }
  }
  else
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x7E,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\periodicupdatemanager.cpp",
      (const char *)v9,
      Size);
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
    {
      v16 = 10;
      v17 = v9;
      goto LABEL_24;
    }
  }
  if ( v19 )
    BiPtFreeMemory();
  return v9;
}

```

## disassembly

```asm
0x180032ed4  push    rbx
0x180032ed6  push    rbp
0x180032ed7  push    rsi
0x180032ed8  push    rdi
0x180032ed9  push    r14
0x180032edb  sub     rsp, 30h
0x180032edf  mov     [rsp+58h+var_30], 0
0x180032ee8  mov     rdi, r9
0x180032eeb  mov     dword ptr [rsp+58h+Size], 0; int
0x180032ef3  mov     r14, r8
0x180032ef6  mov     rbp, rdx
0x180032ef9  mov     rsi, rcx
0x180032efc  test    r9, r9
0x180032eff  jnz     loc_180033066
0x180032f05  lea     r8, [rsp+58h+var_30]
0x180032f0a  lea     rdx, [rsp+58h+Size]
0x180032f0f  call    cs:__imp_BiPtQueryBrokeredEvent
0x180032f15  test    eax, eax
0x180032f17  js      loc_180032FCD
0x180032f1d  xor     ebx, ebx
0x180032f1f  test    ebx, ebx
0x180032f21  jns     short loc_180032F70
0x180032f23  mov     rcx, [rsp+58h]; this
0x180032f28  lea     r8, aOnecoreuapBase_17; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180032f2f  mov     r9d, ebx; char *
0x180032f32  mov     edx, 7Eh ; '~'; void *
0x180032f37  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180032f3c  mov     rcx, cs:WPP_GLOBAL_Control
0x180032f43  lea     rax, WPP_GLOBAL_Control
0x180032f4a  cmp     rcx, rax
0x180032f4d  jnz     loc_180033072
0x180032f53  mov     rcx, [rsp+58h+var_30]
0x180032f58  test    rcx, rcx
0x180032f5b  jz      short loc_180032F63
0x180032f5d  call    cs:__imp_BiPtFreeMemory
0x180032f63  mov     eax, ebx
0x180032f65  add     rsp, 30h
0x180032f69  pop     r14
0x180032f6b  pop     rdi
0x180032f6c  pop     rsi
0x180032f6d  pop     rbp
0x180032f6e  pop     rbx
0x180032f6f  retn
0x180032f70  mov     rdx, [rsp+58h+var_30]
0x180032f75  mov     ebx, 12A4h
0x180032f7a  cmp     [rdx+30h], ebx
0x180032f7d  jnz     short loc_180032FED
0x180032f7f  mov     esi, [rdx+28h]
0x180032f82  add     rsi, rdx
0x180032f85  mov     dword ptr [rsp+58h+Size], ebx; int
0x180032f89  call    cs:__imp_GetProcessHeap
0x180032f8f  mov     r8d, ebx; dwBytes
0x180032f92  xor     edx, edx; dwFlags
0x180032f94  mov     rcx, rax; hHeap
0x180032f97  call    cs:__imp_HeapAlloc
0x180032f9d  mov     rbx, rax
0x180032fa0  test    rax, rax
0x180032fa3  jz      loc_1800330A6
0x180032fa9  mov     rax, [rsp+58h+var_30]
0x180032fae  mov     rcx, rbx; void *
0x180032fb1  mov     r8d, dword ptr [rsp+58h+Size]; Size
0x180032fb6  mov     edx, [rax+2Ch]
0x180032fb9  add     rdx, rax; Src
0x180032fbc  call    memcpy_0
0x180032fc1  test    rbp, rbp
0x180032fc4  jnz     short loc_180033042
0x180032fc6  mov     [r14], rbx
0x180032fc9  xor     ebx, ebx
0x180032fcb  jmp     short loc_180032F53
0x180032fcd  mov     ecx, eax; Status
0x180032fcf  call    cs:__imp_RtlNtStatusToDosError
0x180032fd5  mov     ebx, eax
0x180032fd7  test    eax, eax
0x180032fd9  jle     loc_180032F1F
0x180032fdf  movzx   ebx, ax
0x180032fe2  or      ebx, 80070000h
0x180032fe8  jmp     loc_180032F1F
0x180032fed  mov     rcx, rsi
0x180032ff0  call    cs:__imp_BiPtDeleteEvent
0x180032ff6  mov     rcx, [rsp+58h]; this
0x180032ffb  lea     r8, aOnecoreuapBase_17; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180033002  mov     ebx, 80070057h
0x180033007  mov     edx, 86h; void *
0x18003300c  mov     r9d, ebx; char *
0x18003300f  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180033014  mov     rcx, cs:WPP_GLOBAL_Control
0x18003301b  lea     rax, WPP_GLOBAL_Control
0x180033022  cmp     rcx, rax
0x180033025  jz      loc_180032F53
0x18003302b  test    byte ptr [rcx+1Ch], 80h
0x18003302f  jz      loc_180032F53
0x180033035  mov     edx, 0Bh
0x18003303a  mov     r9d, 80070057h
0x180033040  jmp     short loc_180033091
0x180033042  mov     rdx, rsi; pSid2
0x180033045  mov     rcx, rbp; pSid1
0x180033048  call    cs:__imp_EqualSid
0x18003304e  test    eax, eax
0x180033050  jnz     loc_180032FC6
0x180033056  test    rdi, rdi
0x180033059  jz      loc_180032FC6
0x18003305f  mov     [rdi], eax
0x180033061  jmp     loc_180032FC6
0x180033066  mov     dword ptr [r9], 1
0x18003306d  jmp     loc_180032F05
0x180033072  test    byte ptr [rcx+1Ch], 80h
0x180033076  jz      loc_180032F53
0x18003307c  mov     edx, 0Ah
0x180033081  mov     r9d, ebx
0x180033084  jmp     short loc_180033091
0x180033086  mov     edx, 0Ch
0x18003308b  mov     r9d, 8007000Eh
0x180033091  mov     rcx, [rcx+10h]
0x180033095  lea     r8, WPP_6b3164ff505c38b9d951495712a9c50a_Traceguids
0x18003309c  call    WPP_SF_d
0x1800330a1  jmp     loc_180032F53
0x1800330a6  mov     rcx, [rsp+58h]; this
0x1800330ab  lea     r8, aOnecoreuapBase_17; "onecoreuap\\base\\diagnosis\\platform\\"...
0x1800330b2  mov     ebx, 8007000Eh
0x1800330b7  mov     edx, 8Dh; void *
0x1800330bc  mov     r9d, ebx; char *
0x1800330bf  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800330c4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800330cb  lea     rax, WPP_GLOBAL_Control
0x1800330d2  cmp     rcx, rax
0x1800330d5  jz      loc_180032F53
0x1800330db  test    byte ptr [rcx+1Ch], 80h
0x1800330df  jz      loc_180032F53
0x1800330e5  jmp     short loc_180033086
```
