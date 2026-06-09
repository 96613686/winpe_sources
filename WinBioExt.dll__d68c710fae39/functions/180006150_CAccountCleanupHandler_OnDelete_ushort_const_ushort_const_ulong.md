# CAccountCleanupHandler::OnDelete(ushort const *,ushort const *,ulong)

- ea: `0x180006150`
- end: `0x180006295`
- name: `?OnDelete@CAccountCleanupHandler@@UEAAJPEBG0K@Z`
- size: `325`
- prototype: `signed int __fastcall(CAccountCleanupHandler *this, LPCWSTR StringSid, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180002084`
- `0x180006150`
- `0x180006af0`
- `0x180006b8c`

## import_xrefs

- `ext-ms-win-biometrics-winbio-core-l1-1-0!WinBioGetEnrolledFactors` at `0x180006217`
- `ext-ms-win-biometrics-winbio-core-l1-1-0!WinBioGetEnrolledFactors` at `0x180006217`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000618a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800061d6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000618a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800061d6`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x180006283`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x180006283`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180006180`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180006180`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x1800061cc`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x1800061cc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800061f0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800061f0`

## pseudocode

```c
signed int __fastcall CAccountCleanupHandler::OnDelete(
        CAccountCleanupHandler *this,
        LPCWSTR StringSid,
        const unsigned __int16 *a3)
{
  signed int result; // eax
  signed int EnrolledFactors; // ebx
  PSID v6; // r8
  signed int LastError; // eax
  __int64 *v8; // rdi
  int (*v9)(struct thread_inside_functions *, void *); // rcx
  __int64 v10; // rcx
  PSID Sid; // [rsp+20h] [rbp-38h] BYREF
  _QWORD v12[6]; // [rsp+28h] [rbp-30h] BYREF
  __int64 v13; // [rsp+68h] [rbp+10h] BYREF

  if ( !StringSid )
    return -2147024809;
  Sid = 0;
  if ( ConvertStringSidToSidW(StringSid, &Sid) )
  {
    EnrolledFactors = 0;
    memset_0((char *)this + 16, 0, 0x4Cu);
    v6 = Sid;
    *((_DWORD *)this + 4) = 3;
    if ( !CopySid(0x44u, (char *)this + 24, v6) )
    {
      LastError = GetLastError();
      EnrolledFactors = LastError;
      if ( LastError > 0 )
        EnrolledFactors = (unsigned __int16)LastError | 0x80070000;
    }
    LocalFree(Sid);
    Sid = 0;
    if ( EnrolledFactors >= 0 )
    {
      *((_DWORD *)this + 3) = 0;
      EnrolledFactors = WinBioGetEnrolledFactors((char *)this + 16, (char *)this + 12);
      if ( EnrolledFactors >= 0 )
      {
        if ( *((_DWORD *)this + 3) )
        {
          v8 = (__int64 *)((char *)this + 96);
          v12[0] = 0;
          v13 = *((_QWORD *)this + 12);
          *((_QWORD *)this + 12) = 0;
          handle_thread::Close((handle_thread *)&v13);
          handle_thread::Close((handle_thread *)v12);
          EnrolledFactors = CThread::Create(v9, this, (CAccountCleanupHandler *)((char *)this + 96));
          if ( EnrolledFactors >= 0 )
          {
            v10 = *v8;
            if ( *v8 )
            {
              if ( _InterlockedCompareExchange((volatile signed __int32 *)(v10 + 104), 1, 1) == 1 )
                ResumeThread(*(HANDLE *)(v10 + 8));
            }
          }
        }
      }
    }
    return EnrolledFactors;
  }
  else
  {
    result = GetLastError();
    if ( result > 0 )
      return (unsigned __int16)result | 0x80070000;
  }
  return result;
}

```

## disassembly

```asm
0x180006150  push    rbx
0x180006152  push    rsi
0x180006153  push    rdi
0x180006154  push    r14
0x180006156  sub     rsp, 38h
0x18000615a  mov     rax, rdx
0x18000615d  mov     rsi, rcx
0x180006160  test    rdx, rdx
0x180006163  jnz     short loc_18000616F
0x180006165  mov     eax, 80070057h
0x18000616a  jmp     loc_18000628B
0x18000616f  lea     rdx, [rsp+58h+Sid]; Sid
0x180006174  mov     [rsp+58h+Sid], 0
0x18000617d  mov     rcx, rax; StringSid
0x180006180  call    cs:__imp_ConvertStringSidToSidW
0x180006186  test    eax, eax
0x180006188  jnz     short loc_1800061A5
0x18000618a  call    cs:__imp_GetLastError
0x180006190  test    eax, eax
0x180006192  jle     loc_18000628B
0x180006198  movzx   eax, ax
0x18000619b  or      eax, 80070000h
0x1800061a0  jmp     loc_18000628B
0x1800061a5  xor     ebx, ebx
0x1800061a7  lea     r14, [rsi+10h]
0x1800061ab  xor     edx, edx; Val
0x1800061ad  mov     rcx, r14; void *
0x1800061b0  lea     r8d, [rbx+4Ch]; Size
0x1800061b4  call    memset_0
0x1800061b9  mov     r8, [rsp+58h+Sid]; pSourceSid
0x1800061be  lea     rdx, [r14+8]; pDestinationSid
0x1800061c2  lea     ecx, [rbx+44h]; nDestinationSidLength
0x1800061c5  mov     dword ptr [r14], 3
0x1800061cc  call    cs:__imp_CopySid
0x1800061d2  test    eax, eax
0x1800061d4  jnz     short loc_1800061EB
0x1800061d6  call    cs:__imp_GetLastError
0x1800061dc  mov     ebx, eax
0x1800061de  test    eax, eax
0x1800061e0  jle     short loc_1800061EB
0x1800061e2  movzx   ebx, ax
0x1800061e5  or      ebx, 80070000h
0x1800061eb  mov     rcx, [rsp+58h+Sid]; hMem
0x1800061f0  call    cs:__imp_LocalFree
0x1800061f6  mov     [rsp+58h+Sid], 0
0x1800061ff  test    ebx, ebx
0x180006201  js      loc_180006289
0x180006207  lea     rdi, [rsi+0Ch]
0x18000620b  mov     rcx, r14
0x18000620e  mov     rdx, rdi
0x180006211  mov     dword ptr [rdi], 0
0x180006217  call    cs:__imp_WinBioGetEnrolledFactors
0x18000621d  mov     ebx, eax
0x18000621f  test    eax, eax
0x180006221  js      short loc_180006289
0x180006223  cmp     dword ptr [rdi], 0
0x180006226  jz      short loc_180006289
0x180006228  lea     rdi, [rsi+60h]
0x18000622c  mov     [rsp+58h+var_30], 0
0x180006235  mov     rax, [rdi]
0x180006238  lea     rcx, [rsp+58h+arg_8]; this
0x18000623d  mov     [rsp+58h+arg_8], rax
0x180006242  mov     qword ptr [rdi], 0
0x180006249  call    ?Close@handle_thread@@QEAAXXZ; handle_thread::Close(void)
0x18000624e  lea     rcx, [rsp+58h+var_30]; this
0x180006253  call    ?Close@handle_thread@@QEAAXXZ; handle_thread::Close(void)
0x180006258  mov     r8, rdi; struct handle_thread *
0x18000625b  mov     rdx, rsi; void *
0x18000625e  call    ?Create@CThread@@SAJP6AJAEAVthread_inside_functions@@PEAX@Z1PEAVhandle_thread@@@Z; CThread::Create(long (*)(thread_inside_functions &,void *),void *,handle_thread *)
0x180006263  mov     ebx, eax
0x180006265  test    eax, eax
0x180006267  js      short loc_180006289
0x180006269  mov     rcx, [rdi]
0x18000626c  test    rcx, rcx
0x18000626f  jz      short loc_180006289
0x180006271  mov     edx, 1
0x180006276  mov     eax, edx
0x180006278  lock cmpxchg [rcx+68h], edx
0x18000627d  jnz     short loc_180006289
0x18000627f  mov     rcx, [rcx+8]; hThread
0x180006283  call    cs:__imp_ResumeThread
0x180006289  mov     eax, ebx
0x18000628b  add     rsp, 38h
0x18000628f  pop     r14
0x180006291  pop     rdi
0x180006292  pop     rsi
0x180006293  pop     rbx
0x180006294  retn
```
