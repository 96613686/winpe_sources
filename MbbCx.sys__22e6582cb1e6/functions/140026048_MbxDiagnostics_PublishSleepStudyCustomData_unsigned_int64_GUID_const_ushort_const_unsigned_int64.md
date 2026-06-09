# MbxDiagnostics::PublishSleepStudyCustomData(unsigned __int64,_GUID const *,ushort const *,unsigned __int64)

- ea: `0x140026048`
- end: `0x14002621c`
- name: `?PublishSleepStudyCustomData@MbxDiagnostics@@CAJ_KPEBU_GUID@@PEBG0@Z`
- size: `468`
- prototype: `static int(unsigned __int64, const struct _GUID *, const unsigned __int16 *, unsigned __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x140025854`

## callees

- `0x140001db8`
- `0x140026048`
- `0x140047e50`

## import_xrefs

- `ntoskrnl!RtlInt64ToUnicodeString` at `0x1400260a3`
- `ntoskrnl!RtlInt64ToUnicodeString` at `0x1400260a3`
- `ntoskrnl!EtwWrite` at `0x1400261ce`
- `ntoskrnl!EtwWrite` at `0x1400261ce`

## pseudocode

```c
__int64 __fastcall MbxDiagnostics::PublishSleepStudyCustomData(
        __int64 a1,
        const struct _GUID *a2,
        const unsigned __int16 *a3,
        ULONGLONG a4)
{
  int v6; // edx
  NTSTATUS v7; // ebx
  int v8; // r9d
  __int64 v10; // rcx
  __int64 v11; // rdx
  char v12; // [rsp+30h] [rbp-D0h] BYREF
  int v13; // [rsp+34h] [rbp-CCh] BYREF
  int v14; // [rsp+38h] [rbp-C8h] BYREF
  int v15; // [rsp+3Ch] [rbp-C4h] BYREF
  struct _UNICODE_STRING String; // [rsp+40h] [rbp-C0h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+50h] [rbp-B0h] BYREF
  int *v18; // [rsp+60h] [rbp-A0h]
  __int64 v19; // [rsp+68h] [rbp-98h]
  const struct _GUID *v20; // [rsp+70h] [rbp-90h]
  __int64 v21; // [rsp+78h] [rbp-88h]
  int *v22; // [rsp+80h] [rbp-80h]
  __int64 v23; // [rsp+88h] [rbp-78h]
  const unsigned __int16 *v24; // [rsp+90h] [rbp-70h]
  int v25; // [rsp+98h] [rbp-68h]
  int v26; // [rsp+9Ch] [rbp-64h]
  int *v27; // [rsp+A0h] [rbp-60h]
  __int64 v28; // [rsp+A8h] [rbp-58h]
  _OWORD *v29; // [rsp+B0h] [rbp-50h]
  int v30; // [rsp+B8h] [rbp-48h]
  int v31; // [rsp+BCh] [rbp-44h]
  __int64 *v32; // [rsp+C0h] [rbp-40h]
  __int64 v33; // [rsp+C8h] [rbp-38h]
  _OWORD v34[3]; // [rsp+D0h] [rbp-30h] BYREF
  __int64 v35; // [rsp+140h] [rbp+40h] BYREF

  v35 = a1;
  *(_QWORD *)&String.Length = 2752512;
  String.Buffer = (wchar_t *)v34;
  memset(v34, 0, 42);
  v7 = RtlInt64ToUnicodeString(a4, 0xAu, &String);
  if ( v7 < 0 )
  {
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      return (unsigned int)v7;
    v8 = 18;
LABEL_4:
    LOBYTE(v6) = 2;
    WPP_RECORDER_SF_d(
      WPP_GLOBAL_Control->DeviceExtension,
      v6,
      11,
      v8,
      (__int64)WPP_c0210ef925573523c7eede6d58e7c701_Traceguids,
      v7);
    return (unsigned int)v7;
  }
  v10 = -1;
  v11 = -1;
  do
    ++v11;
  while ( a3[v11] );
  v14 = v11;
  do
    ++v10;
  while ( *((_WORD *)v34 + v10) );
  v12 = v35;
  UserData.Ptr = (ULONGLONG)&v12;
  v18 = &v13;
  v22 = &v14;
  v15 = v10;
  v25 = 2 * v11;
  v13 = 1;
  v27 = &v15;
  v29 = v34;
  v30 = 2 * v10;
  v32 = &v35;
  *(_QWORD *)&UserData.Size = 1;
  v19 = 4;
  v20 = a2;
  v21 = 16;
  v23 = 4;
  v24 = a3;
  v26 = 0;
  v28 = 4;
  v31 = 0;
  v33 = 8;
  v7 = EtwWrite(SLEEPSTUDY_ETW_PROVIDER_Context, &SLEEPSTUDY_EVT_SCENARIO_BLOCKER_DATA, a2, 8u, &UserData);
  if ( v7 < 0 )
  {
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      return (unsigned int)v7;
    v8 = 19;
    goto LABEL_4;
  }
  return 0;
}

```

## disassembly

```asm
0x140026048  mov     [rsp-8+arg_0], rcx
0x14002604d  push    rbp
0x14002604e  push    rbx
0x14002604f  push    rsi
0x140026050  push    rdi
0x140026051  push    r14
0x140026053  lea     rbp, [rsp-10h]
0x140026058  sub     rsp, 110h
0x14002605f  mov     rax, cs:__security_cookie
0x140026066  xor     rax, rsp
0x140026069  mov     [rbp+30h+var_30], rax
0x14002606d  xorps   xmm0, xmm0
0x140026070  mov     qword ptr [rsp+130h+String.Length], 2A0000h
0x140026079  mov     rdi, r8
0x14002607c  lea     rax, [rbp+30h+var_60]
0x140026080  mov     rsi, rdx
0x140026083  mov     [rsp+130h+String.Buffer], rax
0x140026088  movups  xmmword ptr [rbp+30h+var_50], xmm0
0x14002608c  xor     r14d, r14d
0x14002608f  lea     r8, [rsp+130h+String]; String
0x140026094  mov     rcx, r9; Value
0x140026097  movups  [rbp+30h+var_60], xmm0
0x14002609b  lea     edx, [r14+0Ah]; Base
0x14002609f  movups  xmmword ptr [rbp+30h+var_50+0Ah], xmm0
0x1400260a3  call    cs:__imp_RtlInt64ToUnicodeString
0x1400260aa  nop     dword ptr [rax+rax+00h]
0x1400260af  mov     ebx, eax
0x1400260b1  test    eax, eax
0x1400260b3  jns     short loc_1400260F8
0x1400260b5  lea     rcx, WPP_RECORDER_INITIALIZED
0x1400260bc  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x1400260c3  jz      short loc_1400260F1
0x1400260c5  lea     r9d, [r14+12h]
0x1400260c9  lea     rcx, WPP_c0210ef925573523c7eede6d58e7c701_Traceguids
0x1400260d0  mov     [rsp+130h+var_108], ebx
0x1400260d4  mov     [rsp+130h+UserData], rcx
0x1400260d9  mov     r8d, 0Bh
0x1400260df  mov     rcx, cs:WPP_GLOBAL_Control
0x1400260e6  mov     dl, 2
0x1400260e8  mov     rcx, [rcx+40h]
0x1400260ec  call    WPP_RECORDER_SF_d
0x1400260f1  mov     eax, ebx
0x1400260f3  jmp     loc_140026201
0x1400260f8  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1400260fc  mov     rdx, rcx
0x1400260ff  inc     rdx
0x140026102  cmp     [rdi+rdx*2], r14w
0x140026107  jnz     short loc_1400260FF
0x140026109  mov     [rsp+130h+var_F8], edx
0x14002610d  lea     rax, [rbp+30h+var_60]
0x140026111  inc     rcx
0x140026114  cmp     [rax+rcx*2], r14w
0x140026119  jnz     short loc_140026111
0x14002611b  mov     al, byte ptr [rbp+30h+arg_0]
0x14002611e  mov     r8d, 1
0x140026124  mov     [rsp+130h+var_100], al
0x140026128  lea     rax, [rsp+130h+var_100]
0x14002612d  mov     [rsp+130h+var_E0.Ptr], rax
0x140026132  lea     rax, [rsp+130h+var_FC]
0x140026137  mov     [rsp+130h+var_D0], rax
0x14002613c  lea     rax, [rsp+130h+var_F8]
0x140026141  mov     [rbp+30h+var_B0], rax
0x140026145  lea     r9d, [r8+7]; UserDataCount
0x140026149  lea     eax, [rdx+rdx]
0x14002614c  mov     [rsp+130h+var_F4], ecx
0x140026150  mov     [rbp+30h+var_98], eax
0x140026153  lea     rdx, SLEEPSTUDY_EVT_SCENARIO_BLOCKER_DATA; EventDescriptor
0x14002615a  lea     rax, [rsp+130h+var_F4]
0x14002615f  mov     [rsp+130h+var_FC], r8d
0x140026164  mov     [rbp+30h+var_90], rax
0x140026168  lea     rax, [rbp+30h+var_60]
0x14002616c  mov     [rbp+30h+var_80], rax
0x140026170  lea     eax, [rcx+rcx]
0x140026173  mov     rcx, cs:SLEEPSTUDY_ETW_PROVIDER_Context; RegHandle
0x14002617a  mov     [rbp+30h+var_78], eax
0x14002617d  lea     rax, [rbp+30h+arg_0]
0x140026181  mov     [rbp+30h+var_70], rax
0x140026185  lea     rax, [rsp+130h+var_E0]
0x14002618a  mov     qword ptr [rsp+130h+var_E0.Size], r8
0x14002618f  mov     r8, rsi; ActivityId
0x140026192  mov     [rsp+130h+UserData], rax; UserData
0x140026197  mov     [rsp+130h+var_C8], 4
0x1400261a0  mov     [rsp+130h+var_C0], rsi
0x1400261a5  mov     [rsp+130h+var_B8], 10h
0x1400261ae  mov     [rbp+30h+var_A8], 4
0x1400261b6  mov     [rbp+30h+var_A0], rdi
0x1400261ba  mov     [rbp+30h+var_94], r14d
0x1400261be  mov     [rbp+30h+var_88], 4
0x1400261c6  mov     [rbp+30h+var_74], r14d
0x1400261ca  mov     [rbp+30h+var_68], r9
0x1400261ce  call    cs:__imp_EtwWrite
0x1400261d5  nop     dword ptr [rax+rax+00h]
0x1400261da  mov     ebx, eax
0x1400261dc  test    eax, eax
0x1400261de  jns     short loc_1400261FF
0x1400261e0  lea     rcx, WPP_RECORDER_INITIALIZED
0x1400261e7  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x1400261ee  jz      loc_1400260F1
0x1400261f4  mov     r9d, 13h
0x1400261fa  jmp     loc_1400260C9
0x1400261ff  xor     eax, eax
0x140026201  mov     rcx, [rbp+30h+var_30]
0x140026205  xor     rcx, rsp; StackCookie
0x140026208  call    __security_check_cookie
0x14002620d  add     rsp, 110h
0x140026214  pop     r14
0x140026216  pop     rdi
0x140026217  pop     rsi
0x140026218  pop     rbx
0x140026219  pop     rbp
0x14002621a  retn
```
