# Microsoft::CoreUI::Dispatch::UserAdapter::Callback_WaitWorker(Microsoft::CoreUI::Support::Win32Handle *,uint,uint,Microsoft::CoreUI::WaitFlags,CFlat::Ref<uint>)

- ea: `0x180006054`
- end: `0x180006287`
- name: `?Callback_WaitWorker@UserAdapter@Dispatch@CoreUI@Microsoft@@AEAA?AW4WaitStatus@234@PEAUWin32Handle@Support@34@IIW4WaitFlags@34@U?$Ref@I@CFlat@@@Z`
- size: `563`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180008f20`

## callees

- `0x180006054`
- `0x1800067f0`
- `0x180007d80`
- `0x180009750`
- `0x18009d670`
- `0x18009e054`
- `0x1800a236c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x180006178`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x180006178`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180006092`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800060d2`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180006120`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180006092`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800060d2`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180006120`
- `combase!__imp_CoBeginProcessEvents` at `0x18000619d`
- `combase!__imp_CoBeginProcessEvents` at `0x18000619d`
- `combase!__imp_CoMsgWaitInProcessEvents` at `0x1800061be`
- `combase!__imp_CoMsgWaitInProcessEvents` at `0x1800061be`
- `combase!__imp_CoEndProcessEvents` at `0x1800061cf`
- `combase!__imp_CoEndProcessEvents` at `0x1800061cf`
- `ext-ms-win-rtcore-ntuser-synch-ext-l1-1-0!MsgWaitForMultipleObjectsEx` at `0x180006155`
- `ext-ms-win-rtcore-ntuser-synch-ext-l1-1-0!MsgWaitForMultipleObjectsEx` at `0x180006155`

## pseudocode

```c
__int64 __fastcall Microsoft::CoreUI::Dispatch::UserAdapter::Callback_WaitWorker(
        __int64 a1,
        const HANDLE *a2,
        DWORD a3,
        DWORD a4,
        char a5,
        DWORD *a6)
{
  struct _TEB *v9; // rbx
  __int64 SpareUlong0; // rax
  unsigned int v11; // edi
  SIZE_T v12; // rbx
  __int64 v13; // rdx
  __int64 v14; // rcx
  __int64 v15; // r8
  __int64 v16; // r9
  unsigned int v17; // r14d
  DWORD dwFlags; // ebx
  _BYTE *v19; // r12
  _QWORD *Value; // r15
  DWORD v21; // ebx
  Cn::Engine::Lock *v22; // rcx
  __int64 v23; // rdx
  __int64 v24; // rcx
  __int64 v25; // r8
  __int64 v26; // r9
  char v28; // [rsp+30h] [rbp-D8h]
  _BYTE v30[96]; // [rsp+60h] [rbp-A8h] BYREF

  v28 = *(_BYTE *)(*(_QWORD *)(*(_QWORD *)(*((_QWORD *)TlsGetValue(Cn::Context::s_tlsStorage) + 6) + 56LL) + 48LL) + 40LL);
  v9 = NtCurrentTeb();
  SpareUlong0 = (int)v9->SpareUlong0;
  v11 = 0;
  if ( (int)SpareUlong0 < 0 )
    v9 = (struct _TEB *)((char *)v9 + SpareUlong0);
  v12 = v9->Win32ClientInfo[61];
  v14 = *((_QWORD *)TlsGetValue(Cn::Context::s_tlsStorage) + 6);
  if ( *(_QWORD *)(v12 + 8LL * *(unsigned int *)(v14 + 72) + 8) )
    CFlat::Box$1<CFlat::FunctionPointerAndUserData$1<long (*)(void *,unsigned long,void *)>>::GetHashCode(
      v14,
      v13,
      v15,
      v16);
  v17 = -1;
  dwFlags = ~(2 * a5) & 4 | 2;
  if ( (a5 & 1) == 0 )
    dwFlags = ~(2 * a5) & 4;
  v19 = (_BYTE *)(a1 + 52);
  *v19 = 1;
  Value = TlsGetValue(Cn::Context::s_tlsStorage);
  Value[2] = 0;
  CFlat::EntryExit::OnBeginCallToNative(Value);
  if ( v28 )
  {
    memset_0(v30, 0, sizeof(v30));
    CoBeginProcessEvents(v30);
    v21 = CoMsgWaitInProcessEvents(v30, a3, a2, a4, 7423, dwFlags, v28, a4);
    CoEndProcessEvents(v30);
  }
  else
  {
    v21 = MsgWaitForMultipleObjectsEx(a3, a2, a4, 0x1CFFu, dwFlags);
  }
  v22 = (Cn::Engine::Lock *)Value[11];
  if ( v22 )
  {
    Cn::Engine::Lock::Enter(v22);
    if ( !TlsSetValue(Cn::Context::s_tlsStorage, Value) )
      CFlat::Box$1<CFlat::FunctionPointerAndUserData$1<long (*)(void *,unsigned long,void *)>>::GetHashCode(
        v24,
        v23,
        v25,
        v26);
  }
  Value[2] = 0;
  *v19 = 0;
  if ( v21 >= a3 )
  {
    v11 = 128;
    if ( v21 >= 0x80 && v21 < a3 + 128 )
    {
      *a6 = v21 - 128;
    }
    else
    {
      *a6 = 64;
      if ( v21 == a3 )
      {
        return 43962;
      }
      else
      {
        v11 = 192;
        if ( v21 != 192 )
        {
          if ( v21 == 258 )
            return 258;
          return v17;
        }
      }
    }
  }
  else
  {
    *a6 = v21;
  }
  return v11;
}

```

## disassembly

```asm
0x180006054  push    rbx
0x180006056  push    rsi
0x180006057  push    rdi
0x180006058  push    r12
0x18000605a  push    r13
0x18000605c  push    r14
0x18000605e  push    r15
0x180006060  sub     rsp, 0D0h
0x180006067  mov     rax, cs:__security_cookie
0x18000606e  xor     rax, rsp
0x180006071  mov     [rsp+108h+var_48], rax
0x180006079  mov     [rsp+108h+dwMilliseconds], r9d
0x18000607e  mov     esi, r8d
0x180006081  mov     r13, rdx
0x180006084  mov     r12, rcx
0x180006087  mov     [rsp+108h+var_C8], r8d
0x18000608c  mov     ecx, cs:?s_tlsStorage@Context@Cn@@0IA; dwTlsIndex
0x180006092  call    cs:__imp_TlsGetValue
0x180006098  mov     rdx, [rax+30h]
0x18000609c  mov     rax, [rdx+38h]
0x1800060a0  mov     rcx, [rax+30h]
0x1800060a4  mov     al, [rcx+28h]
0x1800060a7  mov     [rsp+108h+var_D8], al
0x1800060ab  mov     rbx, gs:30h
0x1800060b4  movsxd  rax, dword ptr [rbx+180Ch]
0x1800060bb  xor     edi, edi
0x1800060bd  test    eax, eax
0x1800060bf  js      loc_180006279
0x1800060c5  mov     rbx, [rbx+9E8h]
0x1800060cc  mov     ecx, cs:?s_tlsStorage@Context@Cn@@0IA; dwTlsIndex
0x1800060d2  call    cs:__imp_TlsGetValue
0x1800060d8  mov     rcx, [rax+30h]
0x1800060dc  mov     eax, [rcx+48h]
0x1800060df  cmp     [rbx+rax*8+8], rdi
0x1800060e4  jnz     loc_180006281
0x1800060ea  or      r14d, 0FFFFFFFFh
0x1800060ee  mov     [rsp+108h+var_D4], r14d
0x1800060f3  mov     eax, dword ptr [rsp+108h+arg_20]
0x1800060fa  lea     ecx, [rax+rax]
0x1800060fd  not     ecx
0x1800060ff  and     ecx, 4
0x180006102  mov     ebx, ecx
0x180006104  or      ebx, 2
0x180006107  test    al, 1
0x180006109  cmovz   ebx, ecx
0x18000610c  add     r12, 34h ; '4'
0x180006110  mov     [rsp+108h+var_B8], r12
0x180006115  mov     byte ptr [r12], 1
0x18000611a  mov     ecx, cs:?s_tlsStorage@Context@Cn@@0IA; dwTlsIndex
0x180006120  call    cs:__imp_TlsGetValue
0x180006126  mov     r15, rax
0x180006129  mov     [rsp+108h+var_C0], rax
0x18000612e  mov     [rax+10h], rdi
0x180006132  mov     rcx, rax; void *
0x180006135  call    ?OnBeginCallToNative@EntryExit@CFlat@@SAXPEAX@Z; CFlat::EntryExit::OnBeginCallToNative(void *)
0x18000613a  cmp     [rsp+108h+var_D8], dil
0x18000613f  jnz     short loc_180006188
0x180006141  mov     [rsp+108h+dwFlags], ebx; dwFlags
0x180006145  mov     r9d, 1CFFh; dwWakeMask
0x18000614b  mov     r8d, [rsp+108h+dwMilliseconds]; dwMilliseconds
0x180006150  mov     rdx, r13; pHandles
0x180006153  mov     ecx, esi; nCount
0x180006155  call    cs:__imp_MsgWaitForMultipleObjectsEx
0x18000615b  mov     ebx, eax
0x18000615d  mov     [rsp+108h+var_D4], eax
0x180006161  mov     rcx, [r15+58h]; this
0x180006165  test    rcx, rcx
0x180006168  jz      short loc_1800061D7
0x18000616a  call    ?Enter@Lock@Engine@Cn@@QEAAXXZ; Cn::Engine::Lock::Enter(void)
0x18000616f  mov     rdx, r15; lpTlsValue
0x180006172  mov     ecx, cs:?s_tlsStorage@Context@Cn@@0IA; dwTlsIndex
0x180006178  call    cs:__imp_TlsSetValue
0x18000617e  test    eax, eax
0x180006180  jnz     short loc_1800061D7
0x180006182  call    ?GetHashCode@?$Box$1@U?$FunctionPointerAndUserData$1@P6AJPEAXK0@Z@CFlat@@@CFlat@@UEAAHXZ; CFlat::Box$1<CFlat::FunctionPointerAndUserData$1<long (*)(void *,ulong,void *)>>::GetHashCode(void)
0x180006188  xor     edx, edx; Val
0x18000618a  lea     r8d, [rdx+60h]; Size
0x18000618e  lea     rcx, [rsp+108h+var_A8]; void *
0x180006193  call    memset_0
0x180006198  lea     rcx, [rsp+108h+var_A8]
0x18000619d  call    cs:__imp_CoBeginProcessEvents
0x1800061a3  mov     [rsp+108h+var_E0], ebx
0x1800061a7  mov     [rsp+108h+dwFlags], 1CFFh
0x1800061af  mov     r9d, [rsp+108h+dwMilliseconds]
0x1800061b4  mov     r8, r13
0x1800061b7  mov     edx, esi
0x1800061b9  lea     rcx, [rsp+108h+var_A8]
0x1800061be  call    cs:__imp_CoMsgWaitInProcessEvents
0x1800061c4  mov     ebx, eax
0x1800061c6  mov     [rsp+108h+var_D4], eax
0x1800061ca  lea     rcx, [rsp+108h+var_A8]
0x1800061cf  call    cs:__imp_CoEndProcessEvents
0x1800061d5  jmp     short loc_180006161
0x1800061d7  mov     [r15+10h], rdi
0x1800061db  jmp     short loc_1800061F0
0x1800061dd  xor     edi, edi
0x1800061df  or      r14d, 0FFFFFFFFh
0x1800061e3  mov     ebx, [rsp+108h+var_D4]
0x1800061e7  mov     esi, [rsp+108h+var_C8]
0x1800061eb  mov     r12, [rsp+108h+var_B8]
0x1800061f0  mov     [r12], dil
0x1800061f4  cmp     ebx, esi
0x1800061f6  jnb     short loc_180006227
0x1800061f8  mov     rax, [rsp+108h+arg_28]
0x180006200  mov     [rax], ebx
0x180006202  mov     eax, edi
0x180006204  mov     rcx, [rsp+108h+var_48]
0x18000620c  xor     rcx, rsp; StackCookie
0x18000620f  call    __security_check_cookie
0x180006214  add     rsp, 0D0h
0x18000621b  pop     r15
0x18000621d  pop     r14
0x18000621f  pop     r13
0x180006221  pop     r12
0x180006223  pop     rdi
0x180006224  pop     rsi
0x180006225  pop     rbx
0x180006226  retn
0x180006227  mov     edi, 80h
0x18000622c  cmp     ebx, edi
0x18000622e  jb      short loc_18000623A
0x180006230  lea     eax, [rsi+80h]
0x180006236  cmp     ebx, eax
0x180006238  jb      short loc_18000626A
0x18000623a  mov     rax, [rsp+108h+arg_28]
0x180006242  mov     dword ptr [rax], 40h ; '@'
0x180006248  cmp     ebx, esi
0x18000624a  jz      short loc_180006263
0x18000624c  mov     edi, 0C0h
0x180006251  cmp     ebx, edi
0x180006253  jz      short loc_180006202
0x180006255  lea     eax, [rdi+42h]
0x180006258  cmp     ebx, eax
0x18000625a  cmovz   r14d, eax
0x18000625e  mov     edi, r14d
0x180006261  jmp     short loc_180006202
0x180006263  mov     edi, 0ABBAh
0x180006268  jmp     short loc_180006202
0x18000626a  lea     ecx, [rbx-80h]
0x18000626d  mov     rax, [rsp+108h+arg_28]
0x180006275  mov     [rax], ecx
0x180006277  jmp     short loc_180006202
0x180006279  add     rbx, rax
0x18000627c  jmp     loc_1800060C5
0x180006281  call    ?GetHashCode@?$Box$1@U?$FunctionPointerAndUserData$1@P6AJPEAXK0@Z@CFlat@@@CFlat@@UEAAHXZ; CFlat::Box$1<CFlat::FunctionPointerAndUserData$1<long (*)(void *,ulong,void *)>>::GetHashCode(void)
0x1800c8ef8  push    rbp
0x1800c8efa  sub     rsp, 30h
0x1800c8efe  mov     rbp, rdx
0x1800c8f01  mov     rdx, [rbp+48h]; this
0x1800c8f05  call    ?UnexpectedStructuredExceptionFilter@ExceptionHandling@CFlat@@SAHPEAU_EXCEPTION_POINTERS@@PEAX@Z; CFlat::ExceptionHandling::UnexpectedStructuredExceptionFilter(_EXCEPTION_POINTERS *,void *)
0x1800c8f0a  nop
0x1800c8f0b  add     rsp, 30h
0x1800c8f0f  pop     rbp
0x1800c8f10  retn
```
