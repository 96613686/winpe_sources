# DecrementReferenceCount

- ea: `0x1800050b0`
- end: `0x18000526c`
- name: `DecrementReferenceCount`
- size: `444`
- prototype: `__int64 __fastcall(PVOID P)`
- caller_count: `3`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180004230`
- `0x180004e60`
- `0x180005b00`

## callees

- `0x180005060`
- `0x1800050b0`
- `0x180009430`
- `0x18000cd9c`
- `0x18001aa70`
- `0x18001aa9c`
- `0x18001c010`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x18000518f`
- `ntdll!RtlFreeHeap` at `0x18000518f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180005150`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180005150`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180005114`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180005114`

## string_xrefs

- `0x1800051ef`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`
- `0x180005214`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`

## pseudocode

```c
__int64 __fastcall DecrementReferenceCount(volatile signed __int32 *P)
{
  int v2; // eax
  int v3; // eax
  unsigned int v4; // esi
  __int64 v5; // rbx
  int v6; // r8d
  __int64 v7; // rcx
  volatile signed __int32 *v8; // rax
  __int64 v10; // rcx
  void *v11; // rcx

  if ( _InterlockedExchangeAdd(P + 4, 0xFFFFFFFF) != 1 )
    return 0;
  v2 = *((_DWORD *)P + 9);
  if ( v2 == 1 )
  {
LABEL_3:
    v3 = (*((__int64 (__fastcall **)(_QWORD, _QWORD))P + 10))(*((_QWORD *)P + 3), 0);
    v4 = v3;
    if ( v3 < 0 )
    {
      DebugTraceError((unsigned int)v3, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\base.c", 960);
    }
    else
    {
      if ( g_fLoaderInitialized )
      {
        v5 = *((_QWORD *)P + 5);
        if ( v5 )
        {
          EnterCriticalSection(&g_csLoaderLock);
          --*(_DWORD *)(v5 + 16);
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
          {
            WPP_SF_qSD(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              (unsigned int)&WPP_GLOBAL_Control,
              v6,
              v5,
              *(_QWORD *)v5,
              *(_DWORD *)(v5 + 16));
          }
          if ( !*(_DWORD *)(v5 + 16) )
          {
            v10 = *(_QWORD *)(v5 + 8);
            if ( v10 )
              FreeImage(v10);
            RemoveFromLoadedProviderList(v5);
            MSCryptFree(v11);
          }
          LeaveCriticalSection(&g_csLoaderLock);
        }
      }
      v7 = *(unsigned int *)P;
      v8 = P;
      if ( *P )
      {
        do
        {
          *(_BYTE *)v8 = 0;
          v8 = (volatile signed __int32 *)((char *)v8 + 1);
          --v7;
        }
        while ( v7 );
      }
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, (PVOID)P);
    }
  }
  else
  {
    switch ( v2 )
    {
      case 2:
      case 3:
      case 4:
      case 5:
      case 6:
      case 7:
      case 8:
        goto LABEL_3;
      default:
        v4 = -1073741816;
        DebugTraceError(3221225480LL, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\base.c", 951);
        break;
    }
  }
  return v4;
}

```

## disassembly

```asm
0x1800050b0  push    rdi
0x1800050b2  sub     rsp, 30h
0x1800050b6  mov     rdi, rcx
0x1800050b9  mov     eax, 0FFFFFFFFh
0x1800050be  lock xadd [rcx+10h], eax
0x1800050c3  cmp     eax, 1
0x1800050c6  jnz     loc_1800051A9
0x1800050cc  mov     eax, [rcx+24h]
0x1800050cf  mov     [rsp+38h+arg_10], rsi
0x1800050d4  cmp     eax, 1
0x1800050d7  jnz     loc_1800051CA
0x1800050dd  mov     rcx, [rdi+18h]; jumptable 00000001800051E3 cases 2-8
0x1800050e1  xor     edx, edx
0x1800050e3  mov     rax, [rdi+50h]
0x1800050e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800050ec  mov     esi, eax
0x1800050ee  test    eax, eax
0x1800050f0  js      loc_18000520E
0x1800050f6  cmp     cs:g_fLoaderInitialized, 0
0x1800050fd  jz      short loc_180005161
0x1800050ff  mov     [rsp+38h+arg_8], rbx
0x180005104  mov     rbx, [rdi+28h]
0x180005108  test    rbx, rbx
0x18000510b  jz      short loc_18000515C
0x18000510d  lea     rcx, g_csLoaderLock; lpCriticalSection
0x180005114  call    cs:__imp_EnterCriticalSection
0x18000511b  nop     dword ptr [rax+rax+00h]
0x180005120  dec     dword ptr [rbx+10h]
0x180005123  mov     eax, [rbx+10h]
0x180005126  mov     rcx, cs:WPP_GLOBAL_Control
0x18000512d  lea     rdx, WPP_GLOBAL_Control
0x180005134  cmp     rcx, rdx
0x180005137  jz      short loc_18000513F
0x180005139  test    byte ptr [rcx+1Ch], 20h
0x18000513d  jnz     short loc_1800051AD
0x18000513f  cmp     dword ptr [rbx+10h], 0
0x180005143  jz      loc_18000522E
0x180005149  lea     rcx, g_csLoaderLock; lpCriticalSection
0x180005150  call    cs:__imp_LeaveCriticalSection
0x180005157  nop     dword ptr [rax+rax+00h]
0x18000515c  mov     rbx, [rsp+38h+arg_8]
0x180005161  mov     ecx, [rdi]
0x180005163  mov     rax, rdi
0x180005166  test    rcx, rcx
0x180005169  jz      short loc_18000517D
0x18000516b  nop     dword ptr [rax+rax+00h]
0x180005170  mov     byte ptr [rax], 0
0x180005173  lea     rax, [rax+1]
0x180005177  sub     rcx, 1
0x18000517b  jnz     short loc_180005170
0x18000517d  mov     rcx, gs:60h
0x180005186  mov     r8, rdi; P
0x180005189  xor     edx, edx; Flags
0x18000518b  mov     rcx, [rcx+30h]; HeapHandle
0x18000518f  call    cs:__imp_RtlFreeHeap
0x180005196  nop     dword ptr [rax+rax+00h]
0x18000519b  mov     eax, esi
0x18000519d  mov     rsi, [rsp+38h+arg_10]
0x1800051a2  add     rsp, 30h
0x1800051a6  pop     rdi
0x1800051a7  retn
0x1800051a9  xor     eax, eax
0x1800051ab  jmp     short loc_1800051A2
0x1800051ad  mov     rcx, [rcx+10h]
0x1800051b1  mov     r9, rbx
0x1800051b4  mov     [rsp+38h+var_10], eax
0x1800051b8  mov     rax, [rbx]
0x1800051bb  mov     [rsp+38h+var_18], rax
0x1800051c0  call    WPP_SF_qSD
0x1800051c5  jmp     loc_18000513F
0x1800051ca  add     eax, 0FFFFFFFEh; switch 7 cases
0x1800051cd  cmp     eax, 6
0x1800051d0  ja      short def_1800051E3; jumptable 00000001800051E3 default case
0x1800051d2  lea     rcx, __ImageBase
0x1800051d9  mov     eax, ds:(jpt_1800051E3 - 180000000h)[rcx+rax*4]
0x1800051e0  add     rax, rcx
0x1800051e3  jmp     rax; switch jump
0x1800051e9  mov     r9d, 3B7h; jumptable 00000001800051E3 default case
0x1800051ef  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800051f6  lea     rdx, aStatus; "Status"
0x1800051fd  mov     ecx, 0C0000008h
0x180005202  mov     esi, 0C0000008h
0x180005207  call    DebugTraceError
0x18000520c  jmp     short loc_18000519B
0x18000520e  mov     r9d, 3C0h
0x180005214  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000521b  lea     rdx, aStatus; "Status"
0x180005222  mov     ecx, eax
0x180005224  call    DebugTraceError
0x180005229  jmp     loc_18000519B
0x18000522e  mov     rcx, [rbx+8]
0x180005232  test    rcx, rcx
0x180005235  jz      short loc_18000523C
0x180005237  call    _FreeImage
0x18000523c  mov     rcx, rbx
0x18000523f  call    _RemoveFromLoadedProviderList
0x180005244  call    MSCryptFree
0x180005249  jmp     loc_180005149
```
