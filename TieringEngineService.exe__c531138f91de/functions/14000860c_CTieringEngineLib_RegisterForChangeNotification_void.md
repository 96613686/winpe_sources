# CTieringEngineLib::RegisterForChangeNotification(void *)

- ea: `0x14000860c`
- end: `0x14000869e`
- name: `?RegisterForChangeNotification@CTieringEngineLib@@CAJPEAX@Z`
- size: `146`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x140007e80`
- `0x1400086b0`

## callees

- `0x140002db0`
- `0x140004a68`
- `0x14000860c`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x14000868b`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x14000868b`
- `api-ms-win-core-registry-l1-1-0!RegNotifyChangeKeyValue` at `0x140008632`
- `api-ms-win-core-registry-l1-1-0!RegNotifyChangeKeyValue` at `0x140008632`

## pseudocode

```c
__int64 __fastcall CTieringEngineLib::RegisterForChangeNotification(void *a1)
{
  LSTATUS v2; // eax
  unsigned int v3; // ebx
  __int64 v4; // r9

  v2 = RegNotifyChangeKeyValue(*((HKEY *)a1 + 16), 0, 4u, *((HANDLE *)a1 + 15), 1);
  if ( v2 )
  {
    v3 = ATL::AtlHresultFromWin32(v2);
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 108, &WPP_92e7e3ac78e237d967ac9be1c139aa53_Traceguids, v4);
    }
  }
  else
  {
    v3 = 0;
    SetThreadpoolWait(*((PTP_WAIT *)a1 + 14), *((HANDLE *)a1 + 15), 0);
  }
  return v3;
}

```

## disassembly

```asm
0x14000860c  mov     [rsp+arg_0], rbx
0x140008611  push    rdi
0x140008612  sub     rsp, 30h
0x140008616  mov     r9, [rcx+78h]; hEvent
0x14000861a  xor     edx, edx; bWatchSubtree
0x14000861c  mov     rdi, rcx
0x14000861f  mov     [rsp+38h+fAsynchronous], 1; fAsynchronous
0x140008627  mov     rcx, [rcx+80h]; hKey
0x14000862e  lea     r8d, [rdx+4]; dwNotifyFilter
0x140008632  call    cs:__imp_RegNotifyChangeKeyValue
0x140008638  mov     r9d, eax
0x14000863b  test    eax, eax
0x14000863d  jz      short loc_14000867E
0x14000863f  mov     ecx, eax; unsigned int
0x140008641  call    ?AtlHresultFromWin32@ATL@@YAJK@Z; ATL::AtlHresultFromWin32(ulong)
0x140008646  mov     ebx, eax
0x140008648  mov     rcx, cs:WPP_GLOBAL_Control
0x14000864f  lea     rax, WPP_GLOBAL_Control
0x140008656  cmp     rcx, rax
0x140008659  jz      short loc_140008691
0x14000865b  test    byte ptr [rcx+1Ch], 1
0x14000865f  jz      short loc_140008691
0x140008661  cmp     byte ptr [rcx+19h], 2
0x140008665  jb      short loc_140008691
0x140008667  mov     rcx, [rcx+10h]
0x14000866b  lea     r8, WPP_92e7e3ac78e237d967ac9be1c139aa53_Traceguids
0x140008672  mov     edx, 6Ch ; 'l'
0x140008677  call    WPP_SF_d
0x14000867c  jmp     short loc_140008691
0x14000867e  mov     rdx, [rdi+78h]; h
0x140008682  xor     ebx, ebx
0x140008684  mov     rcx, [rdi+70h]; pwa
0x140008688  xor     r8d, r8d; pftTimeout
0x14000868b  call    cs:__imp_SetThreadpoolWait
0x140008691  mov     eax, ebx
0x140008693  mov     rbx, [rsp+38h+arg_0]
0x140008698  add     rsp, 30h
0x14000869c  pop     rdi
0x14000869d  retn
```
