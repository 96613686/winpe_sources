# ChgInit(ushort const *,_INDEX *,int,UNNAMED_STRUCT_CHG * *)

- ea: `0x18000f154`
- end: `0x18000f2a1`
- name: `?ChgInit@@YAKPEBGPEAU_INDEX@@HPEAPEAUUNNAMED_STRUCT_CHG@@@Z`
- size: `333`
- prototype: `__int64 __fastcall(LPCWSTR lpPathName, struct _INDEX *, int, struct UNNAMED_STRUCT_CHG **)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180004320`

## callees

- `0x180001c48`
- `0x180004dec`
- `0x18000f154`
- `0x18000f33c`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18000f1e5`
- `KERNEL32!GetLastError` at `0x18000f238`
- `KERNEL32!GetLastError` at `0x18000f1e5`
- `KERNEL32!GetLastError` at `0x18000f238`
- `KERNEL32!FindFirstChangeNotificationW` at `0x18000f1d6`
- `KERNEL32!FindFirstChangeNotificationW` at `0x18000f1d6`
- `KERNEL32!RegisterWaitForSingleObject` at `0x18000f22e`
- `KERNEL32!RegisterWaitForSingleObject` at `0x18000f22e`

## pseudocode

```c
__int64 __fastcall ChgInit(LPCWSTR lpPathName, struct _INDEX *a2, int a3, struct UNNAMED_STRUCT_CHG **a4)
{
  _QWORD *v8; // rax
  _QWORD *v9; // rbx
  HANDLE v10; // rax
  DWORD LastError; // edi
  _QWORD *v12; // rcx
  __int64 v13; // rdx

  if ( lpPathName && a2 && a4 )
  {
    *a4 = 0;
    v8 = operator new(0x30u, (const struct std::nothrow_t *)&std::nothrow);
    v9 = v8;
    if ( !v8 )
    {
      LastError = 8;
      v9 = 0;
LABEL_18:
      _ChgExit((struct CHG_STRUCT *)v9);
      return LastError;
    }
    v8[1] = a2;
    *(_DWORD *)v8 = 1128808740;
    *((_DWORD *)v8 + 4) = a3;
    v8[3] = -1;
    v8[4] = -1;
    v8[5] = 0;
    v10 = FindFirstChangeNotificationW(lpPathName, 1, 3u);
    v9[3] = v10;
    if ( v10 == (HANDLE)-1LL )
    {
      LastError = GetLastError();
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v13 = 10;
LABEL_13:
        WPP_SF_d(v12[2], v13, WPP_a3cc2cf962863938c4e740311496c24e_Traceguids, LastError);
      }
    }
    else
    {
      if ( RegisterWaitForSingleObject((PHANDLE)v9 + 4, v10, ChangeCallbackThreadProc, v9, 0xFFFFFFFF, 4u) )
      {
        LastError = 0;
        *a4 = (struct UNNAMED_STRUCT_CHG *)v9;
        return LastError;
      }
      LastError = GetLastError();
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v13 = 11;
        goto LABEL_13;
      }
    }
    if ( LastError )
      goto LABEL_18;
    return LastError;
  }
  return 87;
}

```

## disassembly

```asm
0x18000f154  push    rbx
0x18000f156  push    rbp
0x18000f157  push    rsi
0x18000f158  push    rdi
0x18000f159  push    r14
0x18000f15b  sub     rsp, 30h
0x18000f15f  mov     rsi, r9
0x18000f162  mov     r14d, r8d
0x18000f165  mov     rdi, rdx
0x18000f168  mov     rbp, rcx
0x18000f16b  test    rcx, rcx
0x18000f16e  jz      loc_18000F291
0x18000f174  test    rdx, rdx
0x18000f177  jz      loc_18000F291
0x18000f17d  test    r9, r9
0x18000f180  jz      loc_18000F291
0x18000f186  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000f18d  mov     qword ptr [r9], 0
0x18000f194  mov     ecx, 30h ; '0'; unsigned __int64
0x18000f199  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000f19e  mov     rbx, rax
0x18000f1a1  test    rax, rax
0x18000f1a4  jz      loc_18000F27E
0x18000f1aa  mov     [rax+8], rdi
0x18000f1ae  mov     rcx, rbp; lpPathName
0x18000f1b1  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18000f1b5  mov     dword ptr [rax], 43484124h
0x18000f1bb  mov     [rax+10h], r14d
0x18000f1bf  mov     [rax+18h], rdi
0x18000f1c3  mov     [rax+20h], rdi
0x18000f1c7  lea     edx, [rdi+2]; bWatchSubtree
0x18000f1ca  mov     qword ptr [rax+28h], 0
0x18000f1d2  lea     r8d, [rdi+4]; dwNotifyFilter
0x18000f1d6  call    cs:__imp_FindFirstChangeNotificationW
0x18000f1dc  mov     [rbx+18h], rax
0x18000f1e0  cmp     rax, rdi
0x18000f1e3  jnz     short loc_18000F20D
0x18000f1e5  call    cs:__imp_GetLastError
0x18000f1eb  mov     edi, eax
0x18000f1ed  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f1f4  lea     rax, WPP_GLOBAL_Control
0x18000f1fb  cmp     rcx, rax
0x18000f1fe  jz      short loc_18000F271
0x18000f200  test    byte ptr [rcx+1Ch], 1
0x18000f204  jz      short loc_18000F271
0x18000f206  mov     edx, 0Ah
0x18000f20b  jmp     short loc_18000F25E
0x18000f20d  lea     rcx, [rbx+20h]; phNewWaitObject
0x18000f211  mov     [rsp+58h+dwFlags], 4; dwFlags
0x18000f219  mov     r9, rbx; Context
0x18000f21c  mov     [rsp+58h+dwMilliseconds], 0FFFFFFFFh; dwMilliseconds
0x18000f224  lea     r8, ?ChangeCallbackThreadProc@@YAXPEAXE@Z; Callback
0x18000f22b  mov     rdx, rax; hObject
0x18000f22e  call    cs:__imp_RegisterWaitForSingleObject
0x18000f234  test    eax, eax
0x18000f236  jnz     short loc_18000F277
0x18000f238  call    cs:__imp_GetLastError
0x18000f23e  mov     edi, eax
0x18000f240  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f247  lea     rax, WPP_GLOBAL_Control
0x18000f24e  cmp     rcx, rax
0x18000f251  jz      short loc_18000F271
0x18000f253  test    byte ptr [rcx+1Ch], 1
0x18000f257  jz      short loc_18000F271
0x18000f259  mov     edx, 0Bh
0x18000f25e  mov     rcx, [rcx+10h]
0x18000f262  lea     r8, WPP_a3cc2cf962863938c4e740311496c24e_Traceguids
0x18000f269  mov     r9d, edi
0x18000f26c  call    WPP_SF_d
0x18000f271  test    edi, edi
0x18000f273  jz      short loc_18000F28D
0x18000f275  jmp     short loc_18000F285
0x18000f277  xor     edi, edi
0x18000f279  mov     [rsi], rbx
0x18000f27c  jmp     short loc_18000F28D
0x18000f27e  mov     edi, 8
0x18000f283  xor     ebx, ebx
0x18000f285  mov     rcx, rbx; Block
0x18000f288  call    ?_ChgExit@@YAXPEAUCHG_STRUCT@@@Z; _ChgExit(CHG_STRUCT *)
0x18000f28d  mov     eax, edi
0x18000f28f  jmp     short loc_18000F296
0x18000f291  mov     eax, 57h ; 'W'
0x18000f296  add     rsp, 30h
0x18000f29a  pop     r14
0x18000f29c  pop     rdi
0x18000f29d  pop     rsi
0x18000f29e  pop     rbp
0x18000f29f  pop     rbx
0x18000f2a0  retn
```
