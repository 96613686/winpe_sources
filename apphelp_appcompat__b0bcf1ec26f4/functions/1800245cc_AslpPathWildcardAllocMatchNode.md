# AslpPathWildcardAllocMatchNode

- ea: `0x1800245cc`
- end: `0x1800247f4`
- name: `AslpPathWildcardAllocMatchNode`
- size: `552`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180023ae0`
- `0x180034bb0`

## callees

- `0x18000f114`
- `0x1800245cc`
- `0x1800247fc`
- `0x180024924`
- `0x180024a14`
- `0x18003f418`

## import_xrefs

- `ntdll!ZwOpenFile` at `0x18002472b`
- `ntdll!ZwOpenFile` at `0x18002472b`
- `ntdll!RtlAllocateHeap` at `0x180024661`
- `ntdll!RtlAllocateHeap` at `0x180024661`

## string_xrefs

- `0x1800246b6`: `AslpPathWildcardAllocMatchNode`
- `0x1800247ae`: `RtlUnicodeStringCopy failed [%x]`
- `0x180024737`: `Failed to open dir [%x]`

## pseudocode

```c
__int64 __fastcall AslpPathWildcardAllocMatchNode(
        unsigned __int16 *a1,
        _WORD *a2,
        _WORD *a3,
        int a4,
        __int64 a5,
        unsigned __int16 a6)
{
  unsigned __int16 v8; // ax
  unsigned __int16 v9; // cx
  PVOID Heap; // rax
  NTSTATUS v11; // eax
  unsigned int v12; // ebx
  const char *v13; // r9
  __int64 v14; // r8
  __int64 ShareAccess; // [rsp+20h] [rbp-58h]
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+30h] [rbp-48h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+40h] [rbp-38h] BYREF

  memset(&ObjectAttributes, 0, 44);
  IoStatusBlock = 0;
  *(_QWORD *)a1 = 0;
  *((_QWORD *)a1 + 1) = 0;
  *((_QWORD *)a1 + 3) = 0;
  while ( 1 )
  {
    *((_QWORD *)a1 + 2) = a3;
    if ( !*a3 )
      break;
    ++a3;
  }
  *((_QWORD *)a1 + 2) = a3 + 1;
  if ( a3[1] )
  {
    if ( a4 )
    {
      v8 = a6 + *a2;
      if ( v8 < *a2 )
      {
        v11 = -1073741675;
        v13 = "RtlUShortAdd failed [%x]";
        v12 = -1073741675;
        v14 = 2886;
      }
      else
      {
        v9 = v8 + 4;
        if ( (unsigned __int16)(v8 + 4) < v8 )
        {
          v11 = -1073741675;
          v13 = "RtlUShortAdd failed [%x]";
          v12 = -1073741675;
          v14 = 2892;
        }
        else
        {
          a1[1] = v9;
          Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, v9);
          *((_QWORD *)a1 + 1) = Heap;
          if ( !Heap )
          {
            v12 = -1073741801;
            goto LABEL_13;
          }
          v11 = RtlUnicodeStringCopy(a1, a2);
          v12 = v11;
          if ( v11 < 0 )
          {
            v13 = "RtlUnicodeStringCopy failed [%x]";
            v14 = 2907;
          }
          else if ( *(_WORD *)(*((_QWORD *)a1 + 1) + 2 * ((unsigned __int64)*a1 >> 1) - 2) == 92
                 || (v11 = RtlUnicodeStringCatString(a1), v12 = v11, v11 >= 0) )
          {
            if ( a5 && a6 && (v11 = RtlUnicodeStringCbCatStringN(a1, a5, a6), v12 = v11, v11 < 0) )
            {
              v13 = "RtlUnicodeStringCbCatStringN failed [%x]";
              v14 = 2931;
            }
            else
            {
              ObjectAttributes.Length = 48;
              ObjectAttributes.RootDirectory = 0;
              ObjectAttributes.Attributes = 64;
              ObjectAttributes.ObjectName = (PUNICODE_STRING)a1;
              *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
              v11 = ZwOpenFile((PHANDLE)a1 + 3, 0x100001u, &ObjectAttributes, &IoStatusBlock, 1u, 0x21u);
              v12 = v11;
              if ( v11 >= 0 )
                return v12;
              v13 = "Failed to open dir [%x]";
              v14 = 2945;
            }
          }
          else
          {
            v13 = "RtlUnicodeStringCatString failed [%x]";
            v14 = 2923;
          }
        }
      }
      LODWORD(ShareAccess) = v11;
      AslLogCallPrintf(1, "AslpPathWildcardAllocMatchNode", v14, v13, ShareAccess);
    }
    else
    {
      v12 = -1073741565;
    }
  }
  else
  {
    v12 = a4 != 0 ? -1073741638 : -1073741197;
  }
LABEL_13:
  AslpPathWildcardFreeMatchNode(a1);
  return v12;
}

```

## disassembly

```asm
0x1800245cc  push    rbp
0x1800245ce  push    rbx
0x1800245cf  push    rdi
0x1800245d0  push    r14
0x1800245d2  mov     rbp, rsp
0x1800245d5  sub     rsp, 78h
0x1800245d9  xorps   xmm0, xmm0
0x1800245dc  xor     eax, eax
0x1800245de  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x1800245e2  xor     r14d, r14d
0x1800245e5  mov     rbx, rdx
0x1800245e8  movups  xmmword ptr [rbp+ObjectAttributes+1Ch], xmm0
0x1800245ec  mov     rdi, rcx
0x1800245ef  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x1800245f3  movups  xmmword ptr [rbp+IoStatusBlock], xmm0
0x1800245f7  mov     [rcx], r14
0x1800245fa  mov     [rcx+8], r14
0x1800245fe  mov     [rcx+18h], r14
0x180024602  mov     [rcx+10h], r8
0x180024606  cmp     [r8], r14w
0x18002460a  jnz     loc_180024749
0x180024610  lea     rax, [r8+2]
0x180024614  mov     [rcx+10h], rax
0x180024618  cmp     [rax], r14w
0x18002461c  jz      loc_180024784
0x180024622  test    r9d, r9d
0x180024625  jz      loc_18002479A
0x18002462b  movzx   eax, word ptr [rdx]
0x18002462e  add     ax, [rbp+arg_28]
0x180024632  cmp     ax, [rdx]
0x180024635  jb      loc_180024752
0x18002463b  lea     ecx, [rax+4]
0x18002463e  cmp     cx, ax
0x180024641  jb      loc_18002476B
0x180024647  mov     [rdi+2], cx
0x18002464b  mov     edx, 8; Flags
0x180024650  movzx   r8d, cx; Size
0x180024654  mov     rcx, gs:60h
0x18002465d  mov     rcx, [rcx+30h]; HeapHandle
0x180024661  call    cs:__imp_RtlAllocateHeap
0x180024667  mov     [rdi+8], rax
0x18002466b  test    rax, rax
0x18002466e  jz      loc_1800247A4
0x180024674  mov     rdx, rbx
0x180024677  mov     rcx, rdi
0x18002467a  call    RtlUnicodeStringCopy
0x18002467f  mov     ebx, eax
0x180024681  test    eax, eax
0x180024683  js      loc_1800247AE
0x180024689  movzx   ecx, word ptr [rdi]
0x18002468c  mov     rax, [rdi+8]
0x180024690  shr     rcx, 1
0x180024693  cmp     word ptr [rax+rcx*2-2], 5Ch ; '\'
0x180024699  jz      short loc_1800246DF
0x18002469b  mov     rcx, rdi
0x18002469e  call    RtlUnicodeStringCatString
0x1800246a3  mov     ebx, eax
0x1800246a5  test    eax, eax
0x1800246a7  jns     short loc_1800246DF
0x1800246a9  lea     r9, aRtlunicodestri_0; "RtlUnicodeStringCatString failed [%x]"
0x1800246b0  mov     r8d, 0B6Bh
0x1800246b6  lea     rdx, aAslppathwildca_7; "AslpPathWildcardAllocMatchNode"
0x1800246bd  mov     dword ptr [rsp+78h+ShareAccess], eax
0x1800246c1  mov     ecx, 1
0x1800246c6  call    AslLogCallPrintf
0x1800246cb  mov     rcx, rdi
0x1800246ce  call    AslpPathWildcardFreeMatchNode
0x1800246d3  mov     eax, ebx
0x1800246d5  add     rsp, 78h
0x1800246d9  pop     r14
0x1800246db  pop     rdi
0x1800246dc  pop     rbx
0x1800246dd  pop     rbp
0x1800246de  retn
0x1800246df  mov     rdx, [rbp+arg_20]
0x1800246e3  test    rdx, rdx
0x1800246e6  jnz     loc_1800247C0
0x1800246ec  xorps   xmm0, xmm0
0x1800246ef  mov     [rsp+78h+OpenOptions], 21h ; '!'; OpenOptions
0x1800246f7  lea     rcx, [rdi+18h]; FileHandle
0x1800246fb  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x180024702  lea     r9, [rbp+IoStatusBlock]; IoStatusBlock
0x180024706  mov     [rbp+ObjectAttributes.RootDirectory], r14
0x18002470a  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x18002470e  mov     [rbp+ObjectAttributes.Attributes], 40h ; '@'
0x180024715  mov     edx, 100001h; DesiredAccess
0x18002471a  mov     [rbp+ObjectAttributes.ObjectName], rdi
0x18002471e  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x180024723  mov     dword ptr [rsp+78h+ShareAccess], 1; ShareAccess
0x18002472b  call    cs:__imp_ZwOpenFile
0x180024731  mov     ebx, eax
0x180024733  test    eax, eax
0x180024735  jns     short loc_1800246D3
0x180024737  lea     r9, aFailedToOpenDi; "Failed to open dir [%x]"
0x18002473e  mov     r8d, 0B81h
0x180024744  jmp     loc_1800246B6
0x180024749  add     r8, 2
0x18002474d  jmp     loc_180024602
0x180024752  mov     eax, 0C0000095h
0x180024757  lea     r9, aRtlushortaddFa_0; "RtlUShortAdd failed [%x]"
0x18002475e  mov     ebx, eax
0x180024760  mov     r8d, 0B46h
0x180024766  jmp     loc_1800246B6
0x18002476b  mov     eax, 0C0000095h
0x180024770  lea     r9, aRtlushortaddFa_0; "RtlUShortAdd failed [%x]"
0x180024777  mov     ebx, eax
0x180024779  mov     r8d, 0B4Ch
0x18002477f  jmp     loc_1800246B6
0x180024784  neg     r9d
0x180024787  sbb     ebx, ebx
0x180024789  and     ebx, 0FFFFFE47h
0x18002478f  add     ebx, 0C0000273h
0x180024795  jmp     loc_1800246CB
0x18002479a  mov     ebx, 0C0000103h
0x18002479f  jmp     loc_1800246CB
0x1800247a4  mov     ebx, 0C0000017h
0x1800247a9  jmp     loc_1800246CB
0x1800247ae  lea     r9, aRtlunicodestri_2; "RtlUnicodeStringCopy failed [%x]"
0x1800247b5  mov     r8d, 0B5Bh
0x1800247bb  jmp     loc_1800246B6
0x1800247c0  cmp     [rbp+arg_28], r14w
0x1800247c5  jbe     loc_1800246EC
0x1800247cb  movzx   r8d, [rbp+arg_28]
0x1800247d0  mov     rcx, rdi
0x1800247d3  call    RtlUnicodeStringCbCatStringN
0x1800247d8  mov     ebx, eax
0x1800247da  test    eax, eax
0x1800247dc  jns     loc_1800246EC
0x1800247e2  lea     r9, aRtlunicodestri; "RtlUnicodeStringCbCatStringN failed [%x"...
0x1800247e9  mov     r8d, 0B73h
0x1800247ef  jmp     loc_1800246B6
```
