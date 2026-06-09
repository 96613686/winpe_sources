# CNgcReader::GetDevicePropertyString(void *,_DO_DEVINFO_DATA *,_DEVPROPKEY const *,CTextString *)

- ea: `0x18001b5cc`
- end: `0x18001b78d`
- name: `?GetDevicePropertyString@CNgcReader@@KAKPEAXPEAU_DO_DEVINFO_DATA@@PEBU_DEVPROPKEY@@PEAVCTextString@@@Z`
- size: `449`
- prototype: `__int64 __fastcall(void *, struct _DO_DEVINFO_DATA *, const struct _DEVPROPKEY *, struct CTextString *)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops`

## callers

- `0x18001a748`

## callees

- `0x180012740`
- `0x180014b88`
- `0x18001b5cc`
- `0x18001b794`
- `0x18001b7b0`
- `0x180023168`
- `0x18002b7d4`
- `0x1800326d0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b689`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b709`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b689`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b709`
- `DEVOBJ!DevObjGetDeviceProperty` at `0x18001b67f`
- `DEVOBJ!DevObjGetDeviceProperty` at `0x18001b6ff`
- `DEVOBJ!DevObjGetDeviceProperty` at `0x18001b67f`
- `DEVOBJ!DevObjGetDeviceProperty` at `0x18001b6ff`

## string_xrefs

- `0x18001b607`: `CNgcReader::GetDevicePropertyString`

## pseudocode

```c
__int64 __fastcall CNgcReader::GetDevicePropertyString(
        void *a1,
        struct _DO_DEVINFO_DATA *a2,
        const struct _DEVPROPKEY *a3,
        struct CTextString *a4)
{
  DWORD LastError; // ebx
  const WCHAR *v9; // rsi
  const WCHAR *v10; // rax
  void *v11; // rdi
  unsigned int v12; // ebx
  int v14; // [rsp+40h] [rbp-69h] BYREF
  int v15; // [rsp+44h] [rbp-65h] BYREF
  unsigned int v16; // [rsp+48h] [rbp-61h] BYREF
  int v17; // [rsp+4Ch] [rbp-5Dh] BYREF
  _BYTE v18[8]; // [rsp+50h] [rbp-59h] BYREF
  void *Block; // [rsp+58h] [rbp-51h]
  unsigned int v20; // [rsp+60h] [rbp-49h]
  int v21; // [rsp+64h] [rbp-45h]
  _QWORD *v22; // [rsp+68h] [rbp-41h] BYREF
  _QWORD v23[3]; // [rsp+70h] [rbp-39h] BYREF
  char v24[40]; // [rsp+88h] [rbp-21h] BYREF

  v14 = 0;
  v17 = 0;
  strcpy(v24, "CNgcReader::GetDevicePropertyString");
  v23[0] = v24;
  v23[1] = &v17;
  v23[2] = &v14;
  lambda_1270155316cc2726aaa6bc6433732dfc_::operator()(v23);
  v17 = 1;
  v22 = v23;
  v15 = 0;
  v16 = 0;
  if ( !(unsigned int)DevObjGetDeviceProperty(a1, a2, a3, &v15, 0, 0, &v16, 0) )
  {
    LastError = GetLastError();
    v14 = LastError;
    if ( LastError != 122 )
      goto LABEL_17;
    v14 = 0;
  }
  if ( v15 == 18 )
  {
    CBuffer::CBuffer((CBuffer *)v18, v16);
    v9 = &Data;
    v10 = &Data;
    v11 = Block;
    if ( v21 )
      v10 = (const WCHAR *)Block;
    if ( (unsigned int)DevObjGetDeviceProperty(a1, a2, a3, &v15, v10, v21, &v16, 0) )
    {
      if ( v15 == 18 )
      {
        v12 = v16;
        CBuffer::Presize((CBuffer *)v18, v16, 0);
        v20 = v12;
        v11 = Block;
        if ( v21 )
          v9 = (const WCHAR *)Block;
        CTextString::operator=(a4, v9);
        LastError = v14;
      }
      else
      {
        LastError = 13;
        v14 = 13;
      }
    }
    else
    {
      LastError = GetLastError();
      v14 = LastError;
    }
    if ( v11 )
      operator delete[](v11);
  }
  else
  {
    LastError = 13;
    v14 = 13;
  }
LABEL_17:
  WppTraceUnwinder__lambda_1270155316cc2726aaa6bc6433732dfc____::_WppTraceUnwinder__lambda_1270155316cc2726aaa6bc6433732dfc____(&v22);
  return LastError;
}

```

## disassembly

```asm
0x18001b5cc  push    rbp
0x18001b5ce  push    rbx
0x18001b5cf  push    rsi
0x18001b5d0  push    rdi
0x18001b5d1  push    r12
0x18001b5d3  push    r13
0x18001b5d5  push    r14
0x18001b5d7  push    r15
0x18001b5d9  lea     rbp, [rsp-1Fh]
0x18001b5de  sub     rsp, 0C8h
0x18001b5e5  mov     rax, cs:__security_cookie
0x18001b5ec  xor     rax, rsp
0x18001b5ef  mov     [rbp+57h+var_50], rax
0x18001b5f3  mov     r13, r9
0x18001b5f6  mov     r12, r8
0x18001b5f9  mov     r15, rdx
0x18001b5fc  mov     r14, rcx
0x18001b5ff  xor     ebx, ebx
0x18001b601  mov     [rbp+57h+var_C0], ebx
0x18001b604  mov     [rbp+57h+var_B4], ebx
0x18001b607  movups  xmm0, xmmword ptr cs:aCngcreaderGetd; "CNgcReader::GetDevicePropertyString"
0x18001b60e  movups  xmmword ptr [rbp+57h+var_78], xmm0
0x18001b612  movups  xmm1, xmmword ptr cs:aCngcreaderGetd+10h; "evicePropertyString"
0x18001b619  movups  xmmword ptr [rbp+57h+var_78+10h], xmm1
0x18001b61d  mov     eax, dword ptr cs:aCngcreaderGetd+20h; "ing"
0x18001b623  mov     dword ptr [rbp+57h+var_78+20h], eax
0x18001b626  lea     rax, [rbp+57h+var_78]
0x18001b62a  mov     [rbp+57h+var_90], rax
0x18001b62e  lea     rax, [rbp+57h+var_B4]
0x18001b632  mov     [rbp+57h+var_88], rax
0x18001b636  lea     rax, [rbp+57h+var_C0]
0x18001b63a  mov     [rbp+57h+var_80], rax
0x18001b63e  lea     rcx, [rbp+57h+var_90]
0x18001b642  call    _lambda_1270155316cc2726aaa6bc6433732dfc___operator__
0x18001b647  mov     [rbp+57h+var_B4], 1
0x18001b64e  lea     rax, [rbp+57h+var_90]
0x18001b652  mov     [rbp+57h+var_98], rax
0x18001b656  mov     [rbp+57h+var_BC], ebx
0x18001b659  mov     [rbp+57h+var_B8], ebx
0x18001b65c  mov     [rsp+100h+var_C8], ebx
0x18001b660  lea     rax, [rbp+57h+var_B8]
0x18001b664  mov     [rsp+100h+var_D0], rax
0x18001b669  mov     [rsp+100h+var_D8], ebx
0x18001b66d  mov     [rsp+100h+var_E0], rbx
0x18001b672  lea     r9, [rbp+57h+var_BC]
0x18001b676  mov     r8, r12
0x18001b679  mov     rdx, r15
0x18001b67c  mov     rcx, r14
0x18001b67f  call    cs:__imp_DevObjGetDeviceProperty
0x18001b685  test    eax, eax
0x18001b687  jnz     short loc_18001B6A2
0x18001b689  call    cs:__imp_GetLastError
0x18001b68f  mov     ebx, eax
0x18001b691  mov     [rbp+57h+var_C0], eax
0x18001b694  cmp     eax, 7Ah ; 'z'
0x18001b697  jnz     loc_18001B762
0x18001b69d  xor     ebx, ebx
0x18001b69f  mov     [rbp+57h+var_C0], ebx
0x18001b6a2  cmp     [rbp+57h+var_BC], 12h
0x18001b6a6  jz      short loc_18001B6B5
0x18001b6a8  mov     ebx, 0Dh
0x18001b6ad  mov     [rbp+57h+var_C0], ebx
0x18001b6b0  jmp     loc_18001B762
0x18001b6b5  mov     edx, [rbp+57h+var_B8]; unsigned int
0x18001b6b8  lea     rcx, [rbp+57h+var_B0]; this
0x18001b6bc  call    ??0CBuffer@@QEAA@K@Z; CBuffer::CBuffer(ulong)
0x18001b6c1  nop
0x18001b6c2  mov     r9d, [rbp+57h+var_9C]
0x18001b6c6  lea     rsi, Data
0x18001b6cd  mov     rax, rsi
0x18001b6d0  mov     rdi, [rbp+57h+Block]
0x18001b6d4  test    r9d, r9d
0x18001b6d7  cmovnz  rax, rdi
0x18001b6db  mov     [rsp+100h+var_C8], ebx
0x18001b6df  lea     rcx, [rbp+57h+var_B8]
0x18001b6e3  mov     [rsp+100h+var_D0], rcx
0x18001b6e8  mov     [rsp+100h+var_D8], r9d
0x18001b6ed  mov     [rsp+100h+var_E0], rax
0x18001b6f2  lea     r9, [rbp+57h+var_BC]
0x18001b6f6  mov     r8, r12
0x18001b6f9  mov     rdx, r15
0x18001b6fc  mov     rcx, r14
0x18001b6ff  call    cs:__imp_DevObjGetDeviceProperty
0x18001b705  test    eax, eax
0x18001b707  jnz     short loc_18001B716
0x18001b709  call    cs:__imp_GetLastError
0x18001b70f  mov     ebx, eax
0x18001b711  mov     [rbp+57h+var_C0], eax
0x18001b714  jmp     short loc_18001B754
0x18001b716  cmp     [rbp+57h+var_BC], 12h
0x18001b71a  jz      short loc_18001B726
0x18001b71c  mov     ebx, 0Dh
0x18001b721  mov     [rbp+57h+var_C0], ebx
0x18001b724  jmp     short loc_18001B754
0x18001b726  mov     ebx, [rbp+57h+var_B8]
0x18001b729  xor     r8d, r8d; int
0x18001b72c  mov     edx, ebx; unsigned int
0x18001b72e  lea     rcx, [rbp+57h+var_B0]; this
0x18001b732  call    ?Presize@CBuffer@@QEAAPEAEKH@Z; CBuffer::Presize(ulong,int)
0x18001b737  mov     [rbp+57h+var_A0], ebx
0x18001b73a  mov     rdi, [rbp+57h+Block]
0x18001b73e  cmp     [rbp+57h+var_9C], 0
0x18001b742  cmova   rsi, rdi
0x18001b746  mov     rdx, rsi
0x18001b749  mov     rcx, r13
0x18001b74c  call    ??4CTextString@@QEAAPEBGPEBG@Z; CTextString::operator=(ushort const *)
0x18001b751  mov     ebx, [rbp+57h+var_C0]
0x18001b754  test    rdi, rdi
0x18001b757  jz      short loc_18001B762
0x18001b759  mov     rcx, rdi; Block
0x18001b75c  call    ??_V@YAXPEAX@Z; operator delete[](void *)
0x18001b761  nop
0x18001b762  lea     rcx, [rbp+57h+var_98]
0x18001b766  call    WppTraceUnwinder__lambda_1270155316cc2726aaa6bc6433732dfc_______WppTraceUnwinder__lambda_1270155316cc2726aaa6bc6433732dfc____
0x18001b76b  mov     eax, ebx
0x18001b76d  mov     rcx, [rbp+57h+var_50]
0x18001b771  xor     rcx, rsp; StackCookie
0x18001b774  call    __security_check_cookie
0x18001b779  add     rsp, 0C8h
0x18001b780  pop     r15
0x18001b782  pop     r14
0x18001b784  pop     r13
0x18001b786  pop     r12
0x18001b788  pop     rdi
0x18001b789  pop     rsi
0x18001b78a  pop     rbx
0x18001b78b  pop     rbp
0x18001b78c  retn
```
