# EmitStartEvent

- ea: `0x180015664`
- end: `0x180015876`
- name: `EmitStartEvent`
- size: `530`
- prototype: ``
- caller_count: `7`
- callee_count: `6`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1800154ac`
- `0x180053e18`
- `0x180054084`
- `0x18005a410`
- `0x18006056c`
- `0x180067594`
- `0x180067670`

## callees

- `0x180015664`
- `0x18005097c`
- `0x18005b034`
- `0x180065035`
- `0x1800696d4`
- `0x1800810d0`

## import_xrefs

- `msvcrt!??0exception@@QEAA@AEBQEBDH@Z` at `0x1800157fa`
- `msvcrt!??0exception@@QEAA@AEBQEBDH@Z` at `0x1800157fa`
- `RPCRT4!MesHandleFree` at `0x1800157d7`
- `RPCRT4!MesHandleFree` at `0x18001586b`
- `RPCRT4!MesHandleFree` at `0x1800157d7`
- `RPCRT4!MesHandleFree` at `0x18001586b`
- `RPCRT4!MesEncodeDynBufferHandleCreate` at `0x180015729`
- `RPCRT4!MesEncodeDynBufferHandleCreate` at `0x180015729`
- `RPCRT4!NdrMesTypeEncode3` at `0x1800157bc`
- `RPCRT4!NdrMesTypeEncode3` at `0x1800157bc`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
RPC_STATUS __fastcall EmitStartEvent(int a1, int a2, char a3, __int64 a4, int a5, __int64 a6)
{
  RPC_STATUS result; // eax
  int v11; // ecx
  __int16 v12; // r8
  handle_t v13; // rdx
  char *v14; // r9
  unsigned int v15; // ebx
  const char *v16[2]; // [rsp+40h] [rbp-158h] BYREF
  _QWORD v17[3]; // [rsp+50h] [rbp-148h] BYREF
  _BYTE pExceptionObject[208]; // [rsp+68h] [rbp-130h] BYREF
  handle_t pHandle; // [rsp+138h] [rbp-60h] BYREF
  char *pBuffer; // [rsp+140h] [rbp-58h] BYREF
  _DWORD pObject[2]; // [rsp+148h] [rbp-50h] BYREF
  __int64 v22; // [rsp+150h] [rbp-48h]
  unsigned int pEncodedSize; // [rsp+158h] [rbp-40h] BYREF

  v16[1] = (const char *)-2LL;
  result = Microsoft_Windows_Network_SetupEnableBits;
  if ( (Microsoft_Windows_Network_SetupEnableBits & 1) != 0 )
  {
    v11 = a5;
    pObject[0] = a5;
    v12 = 0;
    pObject[1] = 0;
    v22 = a6;
    v13 = 0;
    pHandle = 0;
    v14 = 0;
    pBuffer = 0;
    pEncodedSize = 0;
    if ( a5 )
    {
      v15 = MesEncodeDynBufferHandleCreate(&pBuffer, &pEncodedSize, &pHandle);
      if ( v15 )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_421b3f26bfcd369eac764ae0d92226f2_Traceguids, v15);
        HResultException::HResultException((HResultException *)pExceptionObject, v15 | 0x80010000);
        throw (HResultException *)pExceptionObject;
      }
      NdrMesTypeEncode3(pHandle, &pPicklingInfo, &pProxyInfo, (const unsigned int **)&ArrTypeOffset, 0, pObject);
      v12 = pEncodedSize;
      if ( !pEncodedSize )
      {
        MesHandleFree(pHandle);
        v16[0] = "bad allocation";
        exception::exception((exception *)v17, v16, 1);
        v17[0] = &std::bad_alloc::`vftable';
        throw (std::bad_alloc *)v17;
      }
      v13 = pHandle;
      v14 = pBuffer;
      result = Microsoft_Windows_Network_SetupEnableBits;
    }
    if ( (result & 1) != 0 )
    {
      result = McTemplateU0jqqjhbr4_EventWriteTransfer(v11, (_DWORD)v13, a1, a2, a3, a4, v12, (__int64)v14);
      v13 = pHandle;
    }
    if ( v13 )
      return MesHandleFree(v13);
  }
  return result;
}

```

## disassembly

```asm
0x180015664  push    rbx
0x180015666  push    rsi
0x180015667  push    rdi
0x180015668  push    r14
0x18001566a  push    r15
0x18001566c  sub     rsp, 170h
0x180015673  mov     [rsp+198h+var_150], 0FFFFFFFFFFFFFFFEh
0x18001567c  mov     rax, cs:__security_cookie
0x180015683  xor     rax, rsp
0x180015686  mov     [rsp+198h+var_38], rax
0x18001568e  mov     r15, r9
0x180015691  mov     edi, r8d
0x180015694  mov     r14d, edx
0x180015697  mov     rsi, rcx
0x18001569a  mov     rdx, [rsp+198h+arg_28]
0x1800156a2  mov     eax, cs:Microsoft_Windows_Network_SetupEnableBits
0x1800156a8  test    al, 1
0x1800156aa  jnz     short loc_1800156CB
0x1800156ac  mov     rcx, [rsp+198h+var_38]
0x1800156b4  xor     rcx, rsp; StackCookie
0x1800156b7  call    __security_check_cookie
0x1800156bc  add     rsp, 170h
0x1800156c3  pop     r15
0x1800156c5  pop     r14
0x1800156c7  pop     rdi
0x1800156c8  pop     rsi
0x1800156c9  pop     rbx
0x1800156ca  retn
0x1800156cb  mov     ecx, [rsp+198h+arg_20]
0x1800156d2  mov     [rsp+198h+var_50], ecx
0x1800156d9  xor     r8d, r8d
0x1800156dc  mov     [rsp+198h+var_4C], r8d
0x1800156e4  mov     [rsp+198h+var_48], rdx
0x1800156ec  xor     edx, edx
0x1800156ee  mov     [rsp+198h+pHandle], rdx
0x1800156f6  xor     r9d, r9d
0x1800156f9  mov     [rsp+198h+pBuffer], r9
0x180015701  mov     [rsp+198h+pEncodedSize], r8d
0x180015709  test    ecx, ecx
0x18001570b  jz      loc_180015834
0x180015711  lea     r8, [rsp+198h+pHandle]; pHandle
0x180015719  lea     rdx, [rsp+198h+pEncodedSize]; pEncodedSize
0x180015721  lea     rcx, [rsp+198h+pBuffer]; pBuffer
0x180015729  call    cs:__imp_MesEncodeDynBufferHandleCreate
0x18001572f  mov     ebx, eax
0x180015731  test    eax, eax
0x180015733  jz      short loc_18001578A
0x180015735  lea     rax, WPP_GLOBAL_Control
0x18001573c  mov     rcx, cs:WPP_GLOBAL_Control
0x180015743  cmp     rcx, rax
0x180015746  jz      short loc_180015766
0x180015748  cmp     byte ptr [rcx+19h], 2
0x18001574c  jb      short loc_180015766
0x18001574e  mov     edx, 0Ah
0x180015753  mov     r9d, ebx
0x180015756  lea     r8, WPP_421b3f26bfcd369eac764ae0d92226f2_Traceguids
0x18001575d  mov     rcx, [rcx+10h]
0x180015761  call    WPP_SF_d
0x180015766  or      ebx, 80010000h
0x18001576c  mov     edx, ebx; int
0x18001576e  lea     rcx, [rsp+198h+pExceptionObject]; this
0x180015773  call    ??0HResultException@@QEAA@J@Z; HResultException::HResultException(long)
0x180015778  lea     rdx, _TI3?AVHResultException@@; pThrowInfo
0x18001577f  lea     rcx, [rsp+198h+pExceptionObject]; pExceptionObject
0x180015784  call    _CxxThrowException_0
0x18001578a  lea     rax, [rsp+198h+var_50]
0x180015792  mov     [rsp+198h+pObject], rax; pObject
0x180015797  mov     [rsp+198h+nTypeIndex], 0; nTypeIndex
0x18001579f  lea     r9, ArrTypeOffset; ArrTypeOffset
0x1800157a6  lea     r8, pProxyInfo; pProxyInfo
0x1800157ad  lea     rdx, pPicklingInfo; pPicklingInfo
0x1800157b4  mov     rcx, [rsp+198h+pHandle]; Handle
0x1800157bc  call    cs:__imp_NdrMesTypeEncode3
0x1800157c2  mov     r8d, [rsp+198h+pEncodedSize]
0x1800157ca  test    r8d, r8d
0x1800157cd  jnz     short loc_18001581E
0x1800157cf  mov     rcx, [rsp+198h+pHandle]; Handle
0x1800157d7  call    cs:__imp_MesHandleFree
0x1800157dd  nop
0x1800157de  lea     rax, aBadAllocation; "bad allocation"
0x1800157e5  mov     [rsp+198h+var_158], rax
0x1800157ea  mov     r8d, 1
0x1800157f0  lea     rdx, [rsp+198h+var_158]
0x1800157f5  lea     rcx, [rsp+198h+var_148]
0x1800157fa  call    cs:__imp_??0exception@@QEAA@AEBQEBDH@Z; exception::exception(char const * const &,int)
0x180015800  lea     rax, ??_7bad_alloc@std@@6B@; const std::bad_alloc::`vftable'
0x180015807  mov     [rsp+198h+var_148], rax
0x18001580c  lea     rdx, _TI2?AVbad_alloc@std@@; pThrowInfo
0x180015813  lea     rcx, [rsp+198h+var_148]; pExceptionObject
0x180015818  call    _CxxThrowException_0
0x18001581e  mov     rdx, [rsp+198h+pHandle]
0x180015826  mov     r9, [rsp+198h+pBuffer]
0x18001582e  mov     eax, cs:Microsoft_Windows_Network_SetupEnableBits
0x180015834  test    al, 1
0x180015836  jz      short loc_18001585F
0x180015838  mov     [rsp+198h+var_160], r9
0x18001583d  mov     [rsp+198h+var_168], r8w
0x180015843  mov     [rsp+198h+pObject], r15
0x180015848  mov     [rsp+198h+nTypeIndex], edi
0x18001584c  mov     r9d, r14d
0x18001584f  mov     r8, rsi
0x180015852  call    McTemplateU0jqqjhbr4_EventWriteTransfer
0x180015857  mov     rdx, [rsp+198h+pHandle]
0x18001585f  test    rdx, rdx
0x180015862  jz      loc_1800156AC
0x180015868  mov     rcx, rdx; Handle
0x18001586b  call    cs:__imp_MesHandleFree
0x180015871  jmp     loc_1800156AC
```
