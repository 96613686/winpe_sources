# SiGetBiosSystemPartition

- ea: `0x140025764`
- end: `0x14002589c`
- name: `SiGetBiosSystemPartition`
- size: `312`
- prototype: `__int64 __fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x140013484`

## callees

- `0x14001c8e4`
- `0x14001cf6c`
- `0x1400254d0`
- `0x140025764`

## import_xrefs

- `msvcrt!wcsstr` at `0x1400257c1`
- `msvcrt!wcsstr` at `0x1400257c1`
- `ntdll!RtlFreeHeap` at `0x140025810`
- `ntdll!RtlFreeHeap` at `0x140025831`
- `ntdll!RtlFreeHeap` at `0x140025853`
- `ntdll!RtlFreeHeap` at `0x140025810`
- `ntdll!RtlFreeHeap` at `0x140025831`
- `ntdll!RtlFreeHeap` at `0x140025853`

## pseudocode

```c
__int64 __fastcall SiGetBiosSystemPartition(_QWORD *a1)
{
  void *v1; // rdi
  int BiosSystemDisk; // ebx
  int DriveLayoutInformation; // eax
  _DWORD *v5; // rsi
  wchar_t *v6; // rax
  unsigned int v7; // eax
  _DWORD *v8; // r9
  int v10; // eax
  wchar_t *Str; // [rsp+48h] [rbp+10h] BYREF
  void *v12; // [rsp+50h] [rbp+18h] BYREF
  PVOID P; // [rsp+58h] [rbp+20h] BYREF

  v1 = 0;
  v12 = 0;
  P = 0;
  Str = 0;
  BiosSystemDisk = SiGetBiosSystemDisk(&Str);
  if ( BiosSystemDisk >= 0 )
  {
    DriveLayoutInformation = SiGetDriveLayoutInformation(Str, &P);
    v5 = P;
    BiosSystemDisk = DriveLayoutInformation;
    if ( DriveLayoutInformation >= 0 )
    {
      if ( *(_DWORD *)P )
        goto LABEL_9;
      v6 = wcsstr(Str, L"\\Partition0");
      if ( v6 )
        *v6 = 0;
      v7 = 0;
      v8 = v5 + 12;
      if ( !v5[1] )
      {
LABEL_9:
        BiosSystemDisk = -1073740718;
      }
      else
      {
        while ( !*((_BYTE *)v8 + 33) )
        {
          ++v7;
          v8 += 36;
          if ( v7 >= v5[1] )
            goto LABEL_9;
        }
        v10 = SiAllocateAndPrintf(&v12, L"%s\\Partition%lu", Str, (unsigned int)v8[6]);
        v1 = v12;
        BiosSystemDisk = v10;
        if ( v10 >= 0 )
        {
          *a1 = v12;
          BiosSystemDisk = 0;
        }
      }
    }
    if ( v5 )
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v5);
    if ( BiosSystemDisk < 0 && v1 )
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v1);
  }
  if ( Str )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Str);
  return (unsigned int)BiosSystemDisk;
}

```

## disassembly

```asm
0x140025764  mov     rax, rsp
0x140025767  mov     [rax+8], rbx
0x14002576b  push    rsi
0x14002576c  push    rdi
0x14002576d  push    r14
0x14002576f  sub     rsp, 20h
0x140025773  xor     edi, edi
0x140025775  mov     r14, rcx
0x140025778  lea     rcx, [rax+10h]
0x14002577c  mov     [rax+18h], rdi
0x140025780  mov     [rax+20h], rdi
0x140025784  mov     [rax+10h], rdi
0x140025788  call    SiGetBiosSystemDisk
0x14002578d  mov     ebx, eax
0x14002578f  test    eax, eax
0x140025791  js      loc_140025837
0x140025797  mov     rcx, [rsp+38h+Str]
0x14002579c  lea     rdx, [rsp+38h+P]
0x1400257a1  call    SiGetDriveLayoutInformation
0x1400257a6  mov     rsi, [rsp+38h+P]
0x1400257ab  mov     ebx, eax
0x1400257ad  test    eax, eax
0x1400257af  js      short loc_1400257F9
0x1400257b1  cmp     [rsi], edi
0x1400257b3  jnz     short loc_1400257F4
0x1400257b5  mov     rcx, [rsp+38h+Str]; Str
0x1400257ba  lea     rdx, aPartition0; "\\Partition0"
0x1400257c1  call    cs:__imp_wcsstr
0x1400257c7  test    rax, rax
0x1400257ca  jz      short loc_1400257D1
0x1400257cc  xor     ecx, ecx
0x1400257ce  mov     [rax], cx
0x1400257d1  xor     eax, eax
0x1400257d3  lea     r9, [rsi+30h]
0x1400257d7  cmp     [rsi+4], eax
0x1400257da  jbe     short loc_1400257F4
0x1400257dc  cmp     [r9+21h], dil
0x1400257e0  jnz     loc_140025869
0x1400257e6  inc     eax
0x1400257e8  add     r9, 90h
0x1400257ef  cmp     eax, [rsi+4]
0x1400257f2  jb      short loc_1400257DC
0x1400257f4  mov     ebx, 0C0000452h
0x1400257f9  test    rsi, rsi
0x1400257fc  jz      short loc_140025816
0x1400257fe  mov     rcx, gs:60h
0x140025807  mov     r8, rsi; P
0x14002580a  xor     edx, edx; Flags
0x14002580c  mov     rcx, [rcx+30h]; HeapHandle
0x140025810  call    cs:__imp_RtlFreeHeap
0x140025816  test    ebx, ebx
0x140025818  jns     short loc_140025837
0x14002581a  test    rdi, rdi
0x14002581d  jz      short loc_140025837
0x14002581f  mov     rcx, gs:60h
0x140025828  mov     r8, rdi; P
0x14002582b  xor     edx, edx; Flags
0x14002582d  mov     rcx, [rcx+30h]; HeapHandle
0x140025831  call    cs:__imp_RtlFreeHeap
0x140025837  cmp     [rsp+38h+Str], 0
0x14002583d  jz      short loc_140025859
0x14002583f  mov     rcx, gs:60h
0x140025848  xor     edx, edx; Flags
0x14002584a  mov     r8, [rsp+38h+Str]; P
0x14002584f  mov     rcx, [rcx+30h]; HeapHandle
0x140025853  call    cs:__imp_RtlFreeHeap
0x140025859  mov     eax, ebx
0x14002585b  mov     rbx, [rsp+38h+arg_0]
0x140025860  add     rsp, 20h
0x140025864  pop     r14
0x140025866  pop     rdi
0x140025867  pop     rsi
0x140025868  retn
0x140025869  mov     r9d, [r9+18h]
0x14002586d  lea     rdx, aSPartitionLu; "%s\\Partition%lu"
0x140025874  mov     r8, [rsp+38h+Str]
0x140025879  lea     rcx, [rsp+38h+arg_10]
0x14002587e  call    SiAllocateAndPrintf
0x140025883  mov     rdi, [rsp+38h+arg_10]
0x140025888  mov     ebx, eax
0x14002588a  test    eax, eax
0x14002588c  js      loc_1400257F9
0x140025892  mov     [r14], rdi
0x140025895  xor     ebx, ebx
0x140025897  jmp     loc_1400257F9
```
