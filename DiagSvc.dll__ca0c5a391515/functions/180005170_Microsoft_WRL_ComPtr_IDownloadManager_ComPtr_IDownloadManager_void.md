# Microsoft::WRL::ComPtr<IDownloadManager>::~ComPtr<IDownloadManager>(void)

- ea: `0x180005170`
- end: `0x180005175`
- name: `??1?$ComPtr@UIDownloadManager@@@WRL@Microsoft@@QEAA@XZ`
- size: `5`
- prototype: `void __fastcall(void *)`
- caller_count: `25`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180026390`
- `0x1800263e8`
- `0x1800263fa`
- `0x18002640c`
- `0x180026430`
- `0x180026446`
- `0x18002645c`
- `0x180026581`
- `0x180026593`
- `0x1800265a5`
- `0x1800265b7`
- `0x1800265c9`
- `0x1800265db`
- `0x18002663a`
- `0x18002664c`
- `0x18002665e`
- `0x1800266ca`
- `0x1800266dc`
- `0x1800266ee`
- `0x180026712`
- `0x180026736`
- `0x18002675a`
- `0x18002676c`
- `0x18002677e`
- `0x180026790`

## callees

- `0x18000517c`

## pseudocode

```c
// attributes: thunk
void __fastcall Microsoft::WRL::ComPtr<IDownloadManager>::~ComPtr<IDownloadManager>(void *a1)
{
  Microsoft::WRL::ComPtr<Windows::Web::Http::Headers::IHttpMediaTypeHeaderValueFactory>::InternalRelease(a1);
}

```

## disassembly

```asm
0x180005170  jmp     ?InternalRelease@?$ComPtr@UIHttpMediaTypeHeaderValueFactory@Headers@Http@Web@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Web::Http::Headers::IHttpMediaTypeHeaderValueFactory>::InternalRelease(void)
```
