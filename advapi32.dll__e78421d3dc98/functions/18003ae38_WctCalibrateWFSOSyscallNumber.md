# WctCalibrateWFSOSyscallNumber

- ea: `0x18003ae38`
- end: `0x18003afdb`
- name: `WctCalibrateWFSOSyscallNumber`
- size: `419`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x180039ecc`

## callees

- `0x18003ac90`
- `0x18003ae38`
- `0x18003b1f8`
- `0x18003b57c`
- `0x18003b748`
- `0x18005ff74`
- `0x180065090`

## import_xrefs

- `ntdll!NtQueryInformationThread` at `0x18003af50`
- `ntdll!NtQueryInformationThread` at `0x18003af50`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18003af05`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18003af05`
- `KERNEL32!CreateEventW` at `0x18003aec1`
- `KERNEL32!CreateEventW` at `0x18003aec1`
- `KERNEL32!WaitForSingleObject` at `0x18003af7b`
- `KERNEL32!WaitForSingleObject` at `0x18003af7b`
- `KERNEL32!SetEvent` at `0x18003af6f`
- `KERNEL32!SetEvent` at `0x18003af6f`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 WctCalibrateWFSOSyscallNumber()
{
  unsigned int v0; // edi
  HANDLE EventW; // rax
  HANDLE v2; // rax
  HANDLE v3; // rbx
  DWORD ThreadId; // [rsp+30h] [rbp-39h] BYREF
  ULONG ReturnLength; // [rsp+34h] [rbp-35h] BYREF
  __int64 v7; // [rsp+38h] [rbp-31h] BYREF
  HANDLE ThreadHandle; // [rsp+40h] [rbp-29h] BYREF
  _OWORD Parameter[3]; // [rsp+48h] [rbp-21h] BYREF
  __int64 v10; // [rsp+78h] [rbp+Fh]
  __int128 ThreadInformation; // [rsp+80h] [rbp+17h] BYREF
  __int64 v12; // [rsp+90h] [rbp+27h]

  ThreadInformation = 0;
  v12 = 0;
  ReturnLength = 0;
  ThreadId = 0;
  v0 = -1;
  ThreadHandle = 0;
  v7 = 0;
  memset(Parameter, 0, sizeof(Parameter));
  v10 = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, WPP_4c32fa7a72a13340317baef891270170_Traceguids);
  EventW = CreateEventW(0, 1, 0, 0);
  tlx::unique_any<tlx::file_handle_traits>::reset(&v7, EventW);
  if ( (unsigned __int64)(v7 + 1) > 1 )
  {
    *(_QWORD *)&Parameter[0] = v7;
    v2 = CreateThread(0, 0, WctSyscallCalibratorThreadProc, Parameter, 0, &ThreadId);
    tlx::unique_any<tlx::file_handle_traits>::reset(&ThreadHandle, v2);
    v3 = ThreadHandle;
    if ( (unsigned __int64)ThreadHandle + 1 > 1 )
    {
      if ( (unsigned int)WctWaitUntilThreadIsBlocked(ThreadId)
        && NtQueryInformationThread(v3, ThreadLastSystemCall, &ThreadInformation, 0x18u, &ReturnLength) >= 0
        && ReturnLength == 24
        && WORD4(ThreadInformation) )
      {
        v0 = WORD4(ThreadInformation);
      }
      SetEvent(*(HANDLE *)&Parameter[0]);
      WaitForSingleObject(v3, 0xFFFFFFFF);
    }
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, WPP_4c32fa7a72a13340317baef891270170_Traceguids, v0);
  tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(&v7);
  tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(&ThreadHandle);
  return v0;
}

```

## disassembly

```asm
0x18003ae38  push    rbp
0x18003ae3a  push    rbx
0x18003ae3b  push    rsi
0x18003ae3c  push    rdi
0x18003ae3d  push    r14
0x18003ae3f  lea     rbp, [rsp-37h]
0x18003ae44  sub     rsp, 0A0h
0x18003ae4b  mov     rax, cs:__security_cookie
0x18003ae52  xor     rax, rsp
0x18003ae55  mov     [rbp+57h+var_28], rax
0x18003ae59  xorps   xmm0, xmm0
0x18003ae5c  xor     eax, eax
0x18003ae5e  movups  [rbp+57h+ThreadInformation], xmm0
0x18003ae62  mov     [rbp+57h+var_30], rax
0x18003ae66  xor     esi, esi
0x18003ae68  mov     [rbp+57h+ReturnLength], esi
0x18003ae6b  mov     [rbp+57h+ThreadId], esi
0x18003ae6e  or      edi, 0FFFFFFFFh
0x18003ae71  mov     [rbp+57h+ThreadHandle], rsi
0x18003ae75  mov     [rbp+57h+var_88], rsi
0x18003ae79  movups  [rbp+57h+Parameter], xmm0
0x18003ae7d  movups  [rbp+57h+var_68], xmm0
0x18003ae81  movups  [rbp+57h+var_58], xmm0
0x18003ae85  mov     [rbp+57h+var_48], rax
0x18003ae89  lea     r14, WPP_GLOBAL_Control
0x18003ae90  mov     rcx, cs:WPP_GLOBAL_Control
0x18003ae97  cmp     rcx, r14
0x18003ae9a  jz      short loc_18003AEB5
0x18003ae9c  test    byte ptr [rcx+1Ch], 4
0x18003aea0  jz      short loc_18003AEB5
0x18003aea2  lea     edx, [rax+10h]
0x18003aea5  lea     r8, WPP_4c32fa7a72a13340317baef891270170_Traceguids
0x18003aeac  mov     rcx, [rcx+10h]
0x18003aeb0  call    WPP_SF_
0x18003aeb5  xor     r9d, r9d; lpName
0x18003aeb8  xor     r8d, r8d; bInitialState
0x18003aebb  lea     edx, [r9+1]; bManualReset
0x18003aebf  xor     ecx, ecx; lpEventAttributes
0x18003aec1  call    cs:__imp_CreateEventW
0x18003aec7  mov     rdx, rax
0x18003aeca  lea     rcx, [rbp+57h+var_88]
0x18003aece  call    ?reset@?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAAXPEAX@Z; tlx::unique_any<tlx::file_handle_traits>::reset(void *)
0x18003aed3  mov     rax, [rbp+57h+var_88]
0x18003aed7  lea     rcx, [rax+1]
0x18003aedb  cmp     rcx, 1
0x18003aedf  jbe     loc_18003AF81
0x18003aee5  mov     qword ptr [rbp+57h+Parameter], rax
0x18003aee9  lea     rax, [rbp+57h+ThreadId]
0x18003aeed  mov     [rsp+0C0h+lpThreadId], rax; lpThreadId
0x18003aef2  mov     [rsp+0C0h+dwCreationFlags], esi; dwCreationFlags
0x18003aef6  lea     r9, [rbp+57h+Parameter]; lpParameter
0x18003aefa  lea     r8, WctSyscallCalibratorThreadProc; lpStartAddress
0x18003af01  xor     edx, edx; dwStackSize
0x18003af03  xor     ecx, ecx; lpThreadAttributes
0x18003af05  call    cs:__imp_CreateThread
0x18003af0b  mov     rdx, rax
0x18003af0e  lea     rcx, [rbp+57h+ThreadHandle]
0x18003af12  call    ?reset@?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAAXPEAX@Z; tlx::unique_any<tlx::file_handle_traits>::reset(void *)
0x18003af17  mov     rbx, [rbp+57h+ThreadHandle]
0x18003af1b  lea     rax, [rbx+1]
0x18003af1f  cmp     rax, 1
0x18003af23  jbe     short loc_18003AF81
0x18003af25  mov     edx, 6
0x18003af2a  mov     ecx, [rbp+57h+ThreadId]; unsigned int
0x18003af2d  call    WctWaitUntilThreadIsBlocked
0x18003af32  test    eax, eax
0x18003af34  jz      short loc_18003AF6B
0x18003af36  lea     rax, [rbp+57h+ReturnLength]
0x18003af3a  mov     qword ptr [rsp+0C0h+dwCreationFlags], rax; ReturnLength
0x18003af3f  mov     r9d, 18h; ThreadInformationLength
0x18003af45  lea     r8, [rbp+57h+ThreadInformation]; ThreadInformation
0x18003af49  lea     edx, [r9-3]; ThreadInformationClass
0x18003af4d  mov     rcx, rbx; ThreadHandle
0x18003af50  call    cs:__imp_NtQueryInformationThread
0x18003af56  test    eax, eax
0x18003af58  js      short loc_18003AF6B
0x18003af5a  cmp     [rbp+57h+ReturnLength], 18h
0x18003af5e  jnz     short loc_18003AF6B
0x18003af60  movzx   eax, word ptr [rbp+57h+ThreadInformation+8]
0x18003af64  test    ax, ax
0x18003af67  jz      short loc_18003AF6B
0x18003af69  mov     edi, eax
0x18003af6b  mov     rcx, qword ptr [rbp+57h+Parameter]; hEvent
0x18003af6f  call    cs:__imp_SetEvent
0x18003af75  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18003af78  mov     rcx, rbx; hHandle
0x18003af7b  call    cs:__imp_WaitForSingleObject
0x18003af81  mov     rcx, cs:WPP_GLOBAL_Control
0x18003af88  cmp     rcx, r14
0x18003af8b  jz      short loc_18003AFAC
0x18003af8d  test    byte ptr [rcx+1Ch], 4
0x18003af91  jz      short loc_18003AFAC
0x18003af93  mov     edx, 11h
0x18003af98  mov     r9d, edi
0x18003af9b  lea     r8, WPP_4c32fa7a72a13340317baef891270170_Traceguids
0x18003afa2  mov     rcx, [rcx+10h]
0x18003afa6  call    WPP_SF_d
0x18003afab  nop
0x18003afac  lea     rcx, [rbp+57h+var_88]
0x18003afb0  call    ??1?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(void)
0x18003afb5  nop
0x18003afb6  lea     rcx, [rbp+57h+ThreadHandle]
0x18003afba  call    ??1?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(void)
0x18003afbf  mov     eax, edi
0x18003afc1  mov     rcx, [rbp+57h+var_28]
0x18003afc5  xor     rcx, rsp; StackCookie
0x18003afc8  call    __security_check_cookie
0x18003afcd  add     rsp, 0A0h
0x18003afd4  pop     r14
0x18003afd6  pop     rdi
0x18003afd7  pop     rsi
0x18003afd8  pop     rbx
0x18003afd9  pop     rbp
0x18003afda  retn
```
