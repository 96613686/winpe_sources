# WarbirdRuntime::CEncryption<5,WarbirdCrypto::CCipherFeistel64<28,217,204,126,13,48,223,208,17,214,202,223,18,190,165,137,8,173,218,252,11,62,167,189,14,93,32,35,30,91,149,35,2,231,74,182,24,237,126,169>,WarbirdCrypto::CHashFunctionSCP<1,1,2,2329519407998533220>,WarbirdRuntime::ENCRYPTED_SEGMENT_DATA_CONST_6,WarbirdRuntime::ENCRYPTED_SEGMENT_DATA_READ_WRITE_6>::Decrypt(WarbirdRuntime::ENCRYPTED_SEGMENT_DATA_CONST_6 *,WarbirdRuntime::ENCRYPTED_SEGMENT_DATA_READ_WRITE_6 *)

- ea: `0x180021310`
- end: `0x1800213a0`
- name: `?Decrypt@?$CEncryption@$04V?$CCipherFeistel64@$0BM@$0NJ@$0MM@$0HO@$0N@$0DA@$0NP@$0NA@$0BB@$0NG@$0MK@$0NP@$0BC@$0LO@$0KF@$0IJ@$07$0KN@$0NK@$0PM@$0L@$0DO@$0KH@$0LN@$0O@$0FN@$0CA@$0CD@$0BO@$0FL@$0JF@$0CD@$01$0OH@$0EK@$0LG@$0BI@$0ON@$0HO@$0KJ@@WarbirdCrypto@@V?$CHashFunctionSCP@$00$00$01$0CAFEBNIPCLCBHOGE@@2@UENCRYPTED_SEGMENT_DATA_CONST_6@WarbirdRuntime@@UENCRYPTED_SEGMENT_DATA_READ_WRITE_6@5@@WarbirdRuntime@@SAJPEAUENCRYPTED_SEGMENT_DATA_CONST_6@2@PEAUENCRYPTED_SEGMENT_DATA_READ_WRITE_6@2@@Z`
- size: `144`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180010cf0`

## callees

- `0x180021310`
- `0x180022f00`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180021377`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180021377`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180021331`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180021331`

## pseudocode

```c
__int64 WarbirdRuntime::CEncryption<5,WarbirdCrypto::CCipherFeistel64<28,217,204,126,13,48,223,208,17,214,202,223,18,190,165,137,8,173,218,252,11,62,167,189,14,93,32,35,30,91,149,35,2,231,74,182,24,237,126,169>,WarbirdCrypto::CHashFunctionSCP<1,1,2,2329519407998533220>,WarbirdRuntime::ENCRYPTED_SEGMENT_DATA_CONST_6,WarbirdRuntime::ENCRYPTED_SEGMENT_DATA_READ_WRITE_6>::Decrypt()
{
  int v1; // ebx

  if ( (WarbirdRuntime::g_EncryptedSegmentConstData_65 & 1) == 0 )
    return 0;
  EnterCriticalSection(&WarbirdRuntime::g_encryptionLock);
  if ( WarbirdRuntime::g_EncryptedSegmentReadWriteData_65 )
  {
    v1 = 0;
    if ( WarbirdRuntime::g_EncryptedSegmentReadWriteData_65 != -1 )
      ++WarbirdRuntime::g_EncryptedSegmentReadWriteData_65;
  }
  else
  {
    v1 = WarbirdRuntime::CEncryption<5,WarbirdCrypto::CCipherFeistel64<28,217,204,126,13,48,223,208,17,214,202,223,18,190,165,137,8,173,218,252,11,62,167,189,14,93,32,35,30,91,149,35,2,231,74,182,24,237,126,169>,WarbirdCrypto::CHashFunctionSCP<1,1,2,2329519407998533220>,WarbirdRuntime::ENCRYPTED_SEGMENT_DATA_CONST_6,WarbirdRuntime::ENCRYPTED_SEGMENT_DATA_READ_WRITE_6>::DoCrypt();
    if ( v1 >= 0 )
      WarbirdRuntime::g_EncryptedSegmentReadWriteData_65 = 1;
  }
  LeaveCriticalSection(&WarbirdRuntime::g_encryptionLock);
  return (unsigned int)v1;
}

```

## disassembly

```asm
0x180021310  sub     rsp, 28h
0x180021314  test    cs:?g_EncryptedSegmentConstData_65@WarbirdRuntime@@3UENCRYPTED_SEGMENT_DATA_CONST_6@1@A, 1; WarbirdRuntime::ENCRYPTED_SEGMENT_DATA_CONST_6 WarbirdRuntime::g_EncryptedSegmentConstData_65
0x18002131b  jnz     short loc_180021325
0x18002131d  xor     eax, eax
0x18002131f  add     rsp, 28h
0x180021323  retn
0x180021325  lea     rcx, ?g_encryptionLock@WarbirdRuntime@@3VCLock@1@A; lpCriticalSection
0x18002132c  mov     [rsp+28h+var_8], rbx
0x180021331  call    cs:__imp_EnterCriticalSection
0x180021338  nop     dword ptr [rax+rax+00h]
0x18002133d  mov     eax, cs:?g_EncryptedSegmentReadWriteData_65@WarbirdRuntime@@3UENCRYPTED_SEGMENT_DATA_READ_WRITE_6@1@A; WarbirdRuntime::ENCRYPTED_SEGMENT_DATA_READ_WRITE_6 WarbirdRuntime::g_EncryptedSegmentReadWriteData_65
0x180021343  test    eax, eax
0x180021345  jnz     short loc_180021361
0x180021347  xor     r8d, r8d
0x18002134a  call    ?DoCrypt@?$CEncryption@$04V?$CCipherFeistel64@$0BM@$0NJ@$0MM@$0HO@$0N@$0DA@$0NP@$0NA@$0BB@$0NG@$0MK@$0NP@$0BC@$0LO@$0KF@$0IJ@$07$0KN@$0NK@$0PM@$0L@$0DO@$0KH@$0LN@$0O@$0FN@$0CA@$0CD@$0BO@$0FL@$0JF@$0CD@$01$0OH@$0EK@$0LG@$0BI@$0ON@$0HO@$0KJ@@WarbirdCrypto@@V?$CHashFunctionSCP@$00$00$01$0CAFEBNIPCLCBHOGE@@2@UENCRYPTED_SEGMENT_DATA_CONST_6@WarbirdRuntime@@UENCRYPTED_SEGMENT_DATA_READ_WRITE_6@5@@WarbirdRuntime@@CAJPEAUENCRYPTED_SEGMENT_DATA_CONST_6@2@PEAUENCRYPTED_SEGMENT_DATA_READ_WRITE_6@2@H@Z; WarbirdRuntime::CEncryption<5,WarbirdCrypto::CCipherFeistel64<28,217,204,126,13,48,223,208,17,214,202,223,18,190,165,137,8,173,218,252,11,62,167,189,14,93,32,35,30,91,149,35,2,231,74,182,24,237,126,169>,WarbirdCrypto::CHashFunctionSCP<1,1,2,2329519407998533220>,WarbirdRuntime::ENCRYPTED_SEGMENT_DATA_CONST_6,WarbirdRuntime::ENCRYPTED_SEGMENT_DATA_READ_WRITE_6>::DoCrypt(WarbirdRuntime::ENCRYPTED_SEGMENT_DATA_CONST_6 *,WarbirdRuntime::ENCRYPTED_SEGMENT_DATA_READ_WRITE_6 *,int)
0x18002134f  mov     ebx, eax
0x180021351  test    eax, eax
0x180021353  js      short loc_180021370
0x180021355  mov     cs:?g_EncryptedSegmentReadWriteData_65@WarbirdRuntime@@3UENCRYPTED_SEGMENT_DATA_READ_WRITE_6@1@A, 1; WarbirdRuntime::ENCRYPTED_SEGMENT_DATA_READ_WRITE_6 WarbirdRuntime::g_EncryptedSegmentReadWriteData_65
0x18002135f  jmp     short loc_180021370
0x180021361  xor     ebx, ebx
0x180021363  cmp     eax, 0FFFFFFFFh
0x180021366  jz      short loc_180021370
0x180021368  inc     eax
0x18002136a  mov     cs:?g_EncryptedSegmentReadWriteData_65@WarbirdRuntime@@3UENCRYPTED_SEGMENT_DATA_READ_WRITE_6@1@A, eax; WarbirdRuntime::ENCRYPTED_SEGMENT_DATA_READ_WRITE_6 WarbirdRuntime::g_EncryptedSegmentReadWriteData_65
0x180021370  lea     rcx, ?g_encryptionLock@WarbirdRuntime@@3VCLock@1@A; lpCriticalSection
0x180021377  call    cs:__imp_LeaveCriticalSection
0x18002137e  nop     dword ptr [rax+rax+00h]
0x180021383  mov     eax, ebx
0x180021385  mov     rbx, [rsp+28h+var_8]
0x18002138a  add     rsp, 28h
0x18002138e  retn
```
