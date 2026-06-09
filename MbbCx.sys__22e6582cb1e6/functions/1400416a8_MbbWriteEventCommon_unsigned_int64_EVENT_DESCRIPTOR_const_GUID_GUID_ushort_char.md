# MbbWriteEventCommon(unsigned __int64,_EVENT_DESCRIPTOR const *,_GUID *,_GUID *,ushort,char *)

- ea: `0x1400416a8`
- end: `0x1400417d4`
- name: `?MbbWriteEventCommon@@YAX_KPEBU_EVENT_DESCRIPTOR@@PEAU_GUID@@2GPEAD@Z`
- size: `300`
- prototype: `void __fastcall(REGHANDLE RegHandle, PCEVENT_DESCRIPTOR EventDescriptor, LPCGUID ActivityId, LPCGUID RelatedActivityId, unsigned __int16, char *)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140024338`
- `0x140041664`

## callees

- `0x1400416a8`
- `0x140047e50`

## import_xrefs

- `ntoskrnl!EtwWrite` at `0x140041771`
- `ntoskrnl!EtwWrite` at `0x140041771`
- `ntoskrnl!ExAllocatePool2` at `0x140041712`
- `ntoskrnl!ExAllocatePool2` at `0x140041712`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400417a7`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400417a7`
- `ntoskrnl!EtwWriteTransfer` at `0x14004178c`
- `ntoskrnl!EtwWriteTransfer` at `0x14004178c`

## pseudocode

```c
void __fastcall MbbWriteEventCommon(
        REGHANDLE RegHandle,
        PCEVENT_DESCRIPTOR EventDescriptor,
        LPCGUID ActivityId,
        LPCGUID RelatedActivityId,
        unsigned __int16 a5,
        char *a6)
{
  struct _EVENT_DATA_DESCRIPTOR *UserData; // rbx
  ULONG i; // r10d
  ULONGLONG v13; // rcx
  ULONG v14; // r9d
  __int64 v15; // rax
  struct _EVENT_DATA_DESCRIPTOR P; // [rsp+30h] [rbp-E8h] BYREF

  if ( RegHandle && a5 <= 0x80u )
  {
    if ( a5 > 0xAu )
    {
      UserData = (struct _EVENT_DATA_DESCRIPTOR *)ExAllocatePool2(64, 16LL * a5, 1683505741);
      if ( !UserData )
        return;
    }
    else
    {
      UserData = &P;
    }
    for ( i = 0; i < a5; *(&UserData->Size + 2 * v15) = v14 )
    {
      v13 = *(_QWORD *)a6;
      a6 += 16;
      v14 = *((_DWORD *)a6 - 2);
      v15 = i++;
      v15 *= 2;
      *(&UserData->Ptr + v15) = v13;
    }
    if ( RelatedActivityId )
      EtwWriteTransfer(RegHandle, EventDescriptor, ActivityId, RelatedActivityId, i, UserData);
    else
      EtwWrite(RegHandle, EventDescriptor, ActivityId, i, UserData);
    if ( UserData != &P )
      ExFreePoolWithTag(UserData, 0);
  }
}

```

## disassembly

```asm
0x1400416a8  test    rcx, rcx
0x1400416ab  jz      locret_1400417D2
0x1400416b1  push    rbx
0x1400416b2  push    rbp
0x1400416b3  push    rsi
0x1400416b4  push    rdi
0x1400416b5  push    r14
0x1400416b7  push    r15
0x1400416b9  sub     rsp, 0E8h
0x1400416c0  mov     rax, cs:__security_cookie
0x1400416c7  xor     rax, rsp
0x1400416ca  mov     [rsp+118h+var_48], rax
0x1400416d2  movzx   edi, [rsp+118h+arg_20]
0x1400416da  mov     eax, 80h
0x1400416df  mov     rbp, r9
0x1400416e2  mov     r15, r8
0x1400416e5  mov     r14, rdx
0x1400416e8  mov     rsi, rcx
0x1400416eb  cmp     di, ax
0x1400416ee  ja      loc_1400417B3
0x1400416f4  cmp     edi, 0Ah
0x1400416f7  ja      short loc_140041700
0x1400416f9  lea     rbx, [rsp+118h+P]
0x1400416fe  jmp     short loc_14004172A
0x140041700  mov     rdx, rdi
0x140041703  mov     ecx, 40h ; '@'
0x140041708  shl     rdx, 4
0x14004170c  mov     r8d, 6458424Dh
0x140041712  call    cs:__imp_ExAllocatePool2
0x140041719  nop     dword ptr [rax+rax+00h]
0x14004171e  mov     rbx, rax
0x140041721  test    rax, rax
0x140041724  jz      loc_1400417B3
0x14004172a  xor     r10d, r10d
0x14004172d  test    edi, edi
0x14004172f  jz      short loc_14004175B
0x140041731  mov     r11, [rsp+118h+arg_28]
0x140041739  mov     rcx, [r11]
0x14004173c  lea     r11, [r11+10h]
0x140041740  mov     r9d, [r11-8]
0x140041744  mov     eax, r10d
0x140041747  inc     r10d
0x14004174a  add     rax, rax
0x14004174d  mov     [rbx+rax*8], rcx
0x140041751  mov     [rbx+rax*8+8], r9d
0x140041756  cmp     r10d, edi
0x140041759  jb      short loc_140041739
0x14004175b  mov     r8, r15; ActivityId
0x14004175e  mov     rdx, r14; EventDescriptor
0x140041761  mov     rcx, rsi; RegHandle
0x140041764  test    rbp, rbp
0x140041767  jnz     short loc_14004177F
0x140041769  mov     r9d, r10d; UserDataCount
0x14004176c  mov     [rsp+118h+UserData], rbx; UserData
0x140041771  call    cs:__imp_EtwWrite
0x140041778  nop     dword ptr [rax+rax+00h]
0x14004177d  jmp     short loc_140041798
0x14004177f  mov     [rsp+118h+var_F0], rbx; UserData
0x140041784  mov     r9, rbp; RelatedActivityId
0x140041787  mov     dword ptr [rsp+118h+UserData], r10d; UserDataCount
0x14004178c  call    cs:__imp_EtwWriteTransfer
0x140041793  nop     dword ptr [rax+rax+00h]
0x140041798  lea     rax, [rsp+118h+P]
0x14004179d  cmp     rbx, rax
0x1400417a0  jz      short loc_1400417B3
0x1400417a2  xor     edx, edx; Tag
0x1400417a4  mov     rcx, rbx; P
0x1400417a7  call    cs:__imp_ExFreePoolWithTag
0x1400417ae  nop     dword ptr [rax+rax+00h]
0x1400417b3  mov     rcx, [rsp+118h+var_48]
0x1400417bb  xor     rcx, rsp; StackCookie
0x1400417be  call    __security_check_cookie
0x1400417c3  add     rsp, 0E8h
0x1400417ca  pop     r15
0x1400417cc  pop     r14
0x1400417ce  pop     rdi
0x1400417cf  pop     rsi
0x1400417d0  pop     rbp
0x1400417d1  pop     rbx
0x1400417d2  retn
```
