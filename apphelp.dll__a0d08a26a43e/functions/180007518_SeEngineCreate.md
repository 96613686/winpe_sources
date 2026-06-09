# SeEngineCreate

- ea: `0x180007518`
- end: `0x18000768a`
- name: `SeEngineCreate`
- size: `370`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180002520`
- `0x18001e760`

## callees

- `0x180007518`
- `0x180007690`
- `0x180007734`
- `0x18000781c`
- `0x1800078c0`
- `0x180007a20`
- `0x180007bc4`
- `0x180007c4c`
- `0x18000f114`
- `0x180056ab8`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x180007538`
- `ntdll!RtlAllocateHeap` at `0x180007538`

## string_xrefs

- `0x180007553`: `SeEngineCreate`
- `0x180007617`: `SeEngineCreate`
- `0x18000760b`: `Failed to create Module Tracker`
- `0x180007636`: `Failed to create Shim Manager`
- `0x180007645`: `Failed to create IAT Hook Manager`
- `0x180007654`: `Failed to create Router`
- `0x180007672`: `Failed to create Quirk Manager`
- `0x180007663`: `Failed to create Flag Manager`
- `0x180007681`: `Failed to create Com Router`

## pseudocode

```c
__int64 SeEngineCreate()
{
  _QWORD *Heap; // rax
  _QWORD *v1; // rdi
  int v2; // ebx

  Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, 0x40u);
  v1 = Heap;
  if ( Heap )
  {
    v2 = SeFlagManagerCreate(Heap);
    if ( v2 < 0 )
    {
      AslLogCallPrintf(1, "SeEngineCreate", 227, "Failed to create Flag Manager");
    }
    else
    {
      v2 = SeQuirkManagerCreate(v1 + 1);
      if ( v2 < 0 )
      {
        AslLogCallPrintf(1, "SeEngineCreate", 234, "Failed to create Quirk Manager");
      }
      else
      {
        v2 = SeShimManagerCreate(v1 + 2);
        if ( v2 < 0 )
        {
          AslLogCallPrintf(1, "SeEngineCreate", 250, "Failed to create Shim Manager");
        }
        else
        {
          v2 = SeHookManagerCreate(v1 + 3);
          if ( v2 < 0 )
          {
            AslLogCallPrintf(1, "SeEngineCreate", 257, "Failed to create IAT Hook Manager");
          }
          else
          {
            v2 = SeModuleTrackerCreate(v1 + 5);
            if ( v2 < 0 )
            {
              AslLogCallPrintf(1, "SeEngineCreate", 264, "Failed to create Module Tracker");
            }
            else
            {
              v2 = SeRouterCreate(v1 + 6, v1[3], v1[5]);
              if ( v2 < 0 )
              {
                AslLogCallPrintf(1, "SeEngineCreate", 273, "Failed to create Router");
              }
              else
              {
                v2 = SeComRouterCreate(v1 + 7);
                if ( v2 >= 0 )
                {
                  g_Engine = (__int64)v1;
                  return 0;
                }
                AslLogCallPrintf(1, "SeEngineCreate", 280, "Failed to create Com Router");
              }
            }
          }
        }
      }
    }
    SeEngineDelete(v1);
    return (unsigned int)v2;
  }
  AslLogCallPrintf(1, "SeEngineCreate", 216, "Out of memory");
  return (unsigned int)-1073741801;
}

```

## disassembly

```asm
0x180007518  push    rbx
0x18000751a  push    rsi
0x18000751b  push    rdi
0x18000751c  push    r14
0x18000751e  sub     rsp, 28h
0x180007522  mov     rcx, gs:60h
0x18000752b  mov     edx, 8; Flags
0x180007530  mov     rcx, [rcx+30h]; HeapHandle
0x180007534  lea     r8d, [rdx+38h]; Size
0x180007538  call    cs:__imp_RtlAllocateHeap
0x18000753e  mov     rdi, rax
0x180007541  test    rax, rax
0x180007544  jnz     short loc_180007573
0x180007546  lea     r9, aOutOfMemory; "Out of memory"
0x18000754d  mov     r8d, 0D8h
0x180007553  lea     rdx, aSeenginecreate; "SeEngineCreate"
0x18000755a  lea     ecx, [rax+1]
0x18000755d  call    AslLogCallPrintf
0x180007562  mov     ebx, 0C0000017h
0x180007567  mov     eax, ebx
0x180007569  add     rsp, 28h
0x18000756d  pop     r14
0x18000756f  pop     rdi
0x180007570  pop     rsi
0x180007571  pop     rbx
0x180007572  retn
0x180007573  mov     rcx, rdi
0x180007576  call    SeFlagManagerCreate
0x18000757b  mov     ebx, eax
0x18000757d  test    eax, eax
0x18000757f  js      loc_18000765D
0x180007585  lea     rcx, [rdi+8]
0x180007589  call    SeQuirkManagerCreate
0x18000758e  mov     ebx, eax
0x180007590  test    eax, eax
0x180007592  js      loc_18000766C
0x180007598  lea     rcx, [rdi+10h]
0x18000759c  call    SeShimManagerCreate
0x1800075a1  mov     ebx, eax
0x1800075a3  test    eax, eax
0x1800075a5  js      loc_180007630
0x1800075ab  lea     rcx, [rdi+18h]
0x1800075af  call    SeHookManagerCreate
0x1800075b4  mov     ebx, eax
0x1800075b6  test    eax, eax
0x1800075b8  js      loc_18000763F
0x1800075be  lea     rcx, [rdi+28h]
0x1800075c2  call    SeModuleTrackerCreate
0x1800075c7  mov     ebx, eax
0x1800075c9  test    eax, eax
0x1800075cb  js      short loc_180007605
0x1800075cd  mov     r8, [rdi+28h]
0x1800075d1  lea     rcx, [rdi+30h]
0x1800075d5  mov     rdx, [rdi+18h]
0x1800075d9  call    SeRouterCreate
0x1800075de  mov     ebx, eax
0x1800075e0  test    eax, eax
0x1800075e2  js      short loc_18000764E
0x1800075e4  lea     rcx, [rdi+38h]
0x1800075e8  call    SeComRouterCreate
0x1800075ed  mov     ebx, eax
0x1800075ef  test    eax, eax
0x1800075f1  js      loc_18000767B
0x1800075f7  mov     cs:g_Engine, rdi
0x1800075fe  xor     ebx, ebx
0x180007600  jmp     loc_180007567
0x180007605  mov     r8d, 108h
0x18000760b  lea     r9, aFailedToCreate_16; "Failed to create Module Tracker"
0x180007612  mov     ecx, 1
0x180007617  lea     rdx, aSeenginecreate; "SeEngineCreate"
0x18000761e  call    AslLogCallPrintf
0x180007623  mov     rcx, rdi; P
0x180007626  call    SeEngineDelete
0x18000762b  jmp     loc_180007567
0x180007630  mov     r8d, 0FAh
0x180007636  lea     r9, aFailedToCreate_9; "Failed to create Shim Manager"
0x18000763d  jmp     short loc_180007612
0x18000763f  mov     r8d, 101h
0x180007645  lea     r9, aFailedToCreate_20; "Failed to create IAT Hook Manager"
0x18000764c  jmp     short loc_180007612
0x18000764e  mov     r8d, 111h
0x180007654  lea     r9, aFailedToCreate_15; "Failed to create Router"
0x18000765b  jmp     short loc_180007612
0x18000765d  mov     r8d, 0E3h
0x180007663  lea     r9, aFailedToCreate_5; "Failed to create Flag Manager"
0x18000766a  jmp     short loc_180007612
0x18000766c  mov     r8d, 0EAh
0x180007672  lea     r9, aFailedToCreate_6; "Failed to create Quirk Manager"
0x180007679  jmp     short loc_180007612
0x18000767b  mov     r8d, 118h
0x180007681  lea     r9, aFailedToCreate_28; "Failed to create Com Router"
0x180007688  jmp     short loc_180007612
```
