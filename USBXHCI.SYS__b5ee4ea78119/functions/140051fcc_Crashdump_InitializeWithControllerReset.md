# Crashdump_InitializeWithControllerReset

- ea: `0x140051fcc`
- end: `0x1400521d8`
- name: `Crashdump_InitializeWithControllerReset`
- size: `524`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x140051aa0`

## callees

- `0x14003c6f4`
- `0x14003d168`
- `0x14003d400`
- `0x140051fcc`
- `0x140052fb8`
- `0x140053194`
- `0x140053264`
- `0x140053608`
- `0x1400542f8`
- `0x140055618`
- `0x140055878`
- `0x140055aa8`
- `0x1400560b8`

## import_xrefs

- `ntoskrnl!DbgPrintEx` at `0x1400521b8`
- `ntoskrnl!DbgPrintEx` at `0x1400521b8`

## string_xrefs

- `0x140052058`: `XHCIDUMP: Crashdump_Command_PrepareForDump failed with error 0x%X\n`
- `0x14005209a`: `XHCIDUMP: Crashdump_Command_TestCommandRingOperation failed with error 0x%X\n`

## pseudocode

```c
__int64 __fastcall Crashdump_InitializeWithControllerReset(__int64 a1)
{
  int v2; // eax
  unsigned int v3; // ebx
  __int64 v4; // rdx
  __int64 v5; // xmm1_8
  int v6; // eax
  int started; // eax
  int v8; // eax
  __int64 i; // rsi
  unsigned int v10; // r14d
  __int64 v11; // r12
  int v12; // ebp
  int PortType; // eax
  __int64 v14; // r12
  int v15; // eax
  int v16; // eax
  int v17; // eax
  __int128 v19; // [rsp+20h] [rbp-68h] BYREF
  __int64 v20; // [rsp+30h] [rbp-58h]
  unsigned int v21; // [rsp+90h] [rbp+8h] BYREF

  v21 = 0;
  *(_BYTE *)(a1 + 624) = 1;
  v2 = Crashdump_Register_ResetController();
  v3 = v2;
  if ( v2 >= 0 )
  {
    v4 = *(unsigned int *)(a1 + 408);
    v5 = *(_QWORD *)(a1 + 432);
    v19 = *(_OWORD *)(a1 + 416);
    v20 = v5;
    Crashdump_Register_UpdateDeviceSlotInfo(a1, v4, &v19);
    Crashdump_EventRing_PrepareForDump(a1 + 72);
    v6 = Crashdump_Command_PrepareForDump(a1 + 328);
    v3 = v6;
    if ( v6 >= 0 )
    {
      started = Crashdump_Register_StartController(a1);
      v3 = started;
      if ( started >= 0 )
      {
        Crashdump_Register_LogRHPortInfo(a1, *(unsigned int *)(a1 + 544));
        v8 = Crashdump_Command_TestCommandRingOperation((__int64 *)(a1 + 328));
        v3 = v8;
        if ( v8 >= 0 )
        {
          for ( i = 0; (unsigned int)i < *(_DWORD *)(a1 + 536); i = (unsigned int)(i + 1) )
          {
            v10 = *(_DWORD *)(a1 + 4 * i + 544);
            if ( (_DWORD)i )
            {
              v11 = 376LL * (unsigned int)(i - 1);
              if ( (_DWORD)i == 1 )
              {
                v12 = *(_DWORD *)(a1 + 528);
                v21 = v12;
              }
              else
              {
                PortType = Crashdump_UsbDevice_GetPortType(
                             v11 + *(_QWORD *)(a1 + 568),
                             *(unsigned int *)(a1 + 4LL * (unsigned int)(i - 1) + 544),
                             &v21);
                v3 = PortType;
                if ( PortType < 0 )
                {
                  DbgPrintEx(
                    0x93u,
                    1u,
                    "XHCIDUMP: Crashdump_UsbDevice_GetPortType failed with error 0x%X\n",
                    (unsigned int)PortType);
                  return v3;
                }
                v12 = v21;
              }
              if ( v12 == 20 )
              {
                v14 = *(_QWORD *)(a1 + 568) + v11;
                v15 = Crashdump_UsbDevice_SetPortPower(v14, v10);
                v3 = v15;
                if ( v15 < 0 )
                {
                  DbgPrintEx(
                    0x93u,
                    1u,
                    "XHCIDUMP: Crashdump_UsbDevice_SetPortPower failed with error 0x%X\n",
                    (unsigned int)v15);
                  return v3;
                }
                v16 = Crashdump_UsbDevice_ResetPort(v14, v10, 20);
                v3 = v16;
                if ( v16 < 0 )
                {
                  DbgPrintEx(
                    0x93u,
                    1u,
                    "XHCIDUMP: Crashdump_UsbDevice_ResetPort failed with error 0x%X\n",
                    (unsigned int)v16);
                  return v3;
                }
              }
            }
            else
            {
              v21 = *(_DWORD *)(a1 + 528);
              v12 = v21;
              v17 = Crashdump_Register_ResetPort(a1, v10, v21);
              v3 = v17;
              if ( v17 < 0 )
              {
                DbgPrintEx(
                  0x93u,
                  1u,
                  "XHCIDUMP: Crashdump_Register_ResetPort failed with error 0x%X\n",
                  (unsigned int)v17);
                return v3;
              }
            }
            v3 = Crashdump_UsbDevice_ReConfigureOnControllerReset(*(_QWORD *)(a1 + 568) + 376LL * (unsigned int)i, v12);
            if ( (v3 & 0x80000000) != 0 )
              return v3;
          }
        }
        else
        {
          DbgPrintEx(
            0x93u,
            1u,
            "XHCIDUMP: Crashdump_Command_TestCommandRingOperation failed with error 0x%X\n",
            (unsigned int)v8);
        }
      }
      else
      {
        DbgPrintEx(
          0x93u,
          1u,
          "XHCIDUMP: Crashdump_Register_StartController failed with error 0x%X\n",
          (unsigned int)started);
      }
    }
    else
    {
      DbgPrintEx(0x93u, 1u, "XHCIDUMP: Crashdump_Command_PrepareForDump failed with error 0x%X\n", (unsigned int)v6);
    }
  }
  else
  {
    DbgPrintEx(0x93u, 1u, "XHCIDUMP: Crashdump_Register_ResetController failed with error 0x%X\n", (unsigned int)v2);
  }
  return v3;
}

```

## disassembly

```asm
0x140051fcc  mov     rax, rsp
0x140051fcf  push    rbx
0x140051fd0  push    rbp
0x140051fd1  push    rsi
0x140051fd2  push    rdi
0x140051fd3  push    r12
0x140051fd5  push    r13
0x140051fd7  push    r14
0x140051fd9  push    r15
0x140051fdb  sub     rsp, 48h
0x140051fdf  mov     r13d, 1
0x140051fe5  mov     dword ptr [rax+8], 0
0x140051fec  mov     [rcx+270h], r13b
0x140051ff3  mov     rdi, rcx
0x140051ff6  call    Crashdump_Register_ResetController
0x140051ffb  mov     ebx, eax
0x140051ffd  test    eax, eax
0x140051fff  jns     short loc_14005200D
0x140052001  lea     r8, aXhcidumpCrashd_71; "XHCIDUMP: Crashdump_Register_ResetContr"...
0x140052008  jmp     loc_1400521AD
0x14005200d  movups  xmm0, xmmword ptr [rdi+1A0h]
0x140052014  lea     r8, [rsp+88h+var_68]
0x140052019  mov     edx, [rdi+198h]
0x14005201f  movsd   xmm1, qword ptr [rdi+1B0h]
0x140052027  mov     rcx, rdi
0x14005202a  movaps  [rsp+88h+var_68], xmm0
0x14005202f  movsd   [rsp+88h+var_58], xmm1
0x140052035  call    Crashdump_Register_UpdateDeviceSlotInfo
0x14005203a  lea     rcx, [rdi+48h]
0x14005203e  call    Crashdump_EventRing_PrepareForDump
0x140052043  lea     rsi, [rdi+148h]
0x14005204a  mov     rcx, rsi
0x14005204d  call    Crashdump_Command_PrepareForDump
0x140052052  mov     ebx, eax
0x140052054  test    eax, eax
0x140052056  jns     short loc_140052064
0x140052058  lea     r8, aXhcidumpCrashd_42; "XHCIDUMP: Crashdump_Command_PrepareForD"...
0x14005205f  jmp     loc_1400521AD
0x140052064  mov     rcx, rdi
0x140052067  call    Crashdump_Register_StartController
0x14005206c  mov     ebx, eax
0x14005206e  test    eax, eax
0x140052070  jns     short loc_14005207E
0x140052072  lea     r8, aXhcidumpCrashd_67; "XHCIDUMP: Crashdump_Register_StartContr"...
0x140052079  jmp     loc_1400521AD
0x14005207e  mov     edx, [rdi+220h]
0x140052084  mov     rcx, rdi
0x140052087  call    Crashdump_Register_LogRHPortInfo
0x14005208c  mov     rcx, rsi
0x14005208f  call    Crashdump_Command_TestCommandRingOperation
0x140052094  mov     ebx, eax
0x140052096  test    eax, eax
0x140052098  jns     short loc_1400520A6
0x14005209a  lea     r8, aXhcidumpCrashd_54; "XHCIDUMP: Crashdump_Command_TestCommand"...
0x1400520a1  jmp     loc_1400521AD
0x1400520a6  xor     esi, esi
0x1400520a8  cmp     esi, [rdi+218h]
0x1400520ae  jnb     loc_1400521C4
0x1400520b4  mov     r14d, [rdi+rsi*4+220h]
0x1400520bc  mov     r15d, esi
0x1400520bf  test    esi, esi
0x1400520c1  jz      loc_140052150
0x1400520c7  lea     eax, [rsi-1]
0x1400520ca  mov     edx, eax
0x1400520cc  imul    r12, rdx, 178h
0x1400520d3  cmp     esi, r13d
0x1400520d6  jnz     short loc_1400520E7
0x1400520d8  mov     ebp, [rdi+210h]
0x1400520de  mov     [rsp+88h+arg_0], ebp
0x1400520e5  jmp     short loc_140052116
0x1400520e7  mov     rcx, [rdi+238h]
0x1400520ee  lea     r8, [rsp+88h+arg_0]
0x1400520f6  mov     edx, [rdi+rax*4+220h]
0x1400520fd  add     rcx, r12
0x140052100  call    Crashdump_UsbDevice_GetPortType
0x140052105  mov     ebx, eax
0x140052107  test    eax, eax
0x140052109  js      loc_14005219D
0x14005210f  mov     ebp, [rsp+88h+arg_0]
0x140052116  cmp     ebp, 14h
0x140052119  jnz     short loc_140052171
0x14005211b  add     r12, [rdi+238h]
0x140052122  mov     edx, r14d
0x140052125  mov     rcx, r12
0x140052128  call    Crashdump_UsbDevice_SetPortPower
0x14005212d  mov     ebx, eax
0x14005212f  test    eax, eax
0x140052131  js      short loc_140052194
0x140052133  mov     r8d, ebp
0x140052136  mov     edx, r14d
0x140052139  mov     rcx, r12
0x14005213c  call    Crashdump_UsbDevice_ResetPort
0x140052141  mov     ebx, eax
0x140052143  test    eax, eax
0x140052145  jns     short loc_140052171
0x140052147  lea     r8, aXhcidumpCrashd_95; "XHCIDUMP: Crashdump_UsbDevice_ResetPort"...
0x14005214e  jmp     short loc_1400521AD
0x140052150  mov     ebp, [rdi+210h]
0x140052156  mov     edx, r14d
0x140052159  mov     r8d, ebp
0x14005215c  mov     [rsp+88h+arg_0], ebp
0x140052163  mov     rcx, rdi
0x140052166  call    Crashdump_Register_ResetPort
0x14005216b  mov     ebx, eax
0x14005216d  test    eax, eax
0x14005216f  js      short loc_1400521A6
0x140052171  imul    rcx, r15, 178h
0x140052178  mov     edx, ebp
0x14005217a  add     rcx, [rdi+238h]
0x140052181  call    Crashdump_UsbDevice_ReConfigureOnControllerReset
0x140052186  mov     ebx, eax
0x140052188  test    eax, eax
0x14005218a  js      short loc_1400521C4
0x14005218c  add     esi, r13d
0x14005218f  jmp     loc_1400520A8
0x140052194  lea     r8, aXhcidumpCrashd_11; "XHCIDUMP: Crashdump_UsbDevice_SetPortPo"...
0x14005219b  jmp     short loc_1400521AD
0x14005219d  lea     r8, aXhcidumpCrashd_16; "XHCIDUMP: Crashdump_UsbDevice_GetPortTy"...
0x1400521a4  jmp     short loc_1400521AD
0x1400521a6  lea     r8, aXhcidumpCrashd_91; "XHCIDUMP: Crashdump_Register_ResetPort "...
0x1400521ad  mov     r9d, eax
0x1400521b0  mov     edx, r13d; Level
0x1400521b3  mov     ecx, 93h; ComponentId
0x1400521b8  call    cs:__imp_DbgPrintEx
0x1400521bf  nop     dword ptr [rax+rax+00h]
0x1400521c4  mov     eax, ebx
0x1400521c6  add     rsp, 48h
0x1400521ca  pop     r15
0x1400521cc  pop     r14
0x1400521ce  pop     r13
0x1400521d0  pop     r12
0x1400521d2  pop     rdi
0x1400521d3  pop     rsi
0x1400521d4  pop     rbp
0x1400521d5  pop     rbx
0x1400521d6  retn
```
